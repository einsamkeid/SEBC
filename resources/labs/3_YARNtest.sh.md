```
#!/bin/sh
# Confirm the path values given below correspond to your installation

HADOOP_MR=/opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce
HADOOP_PATH=/opt/cloudera/parcels/CDH/bin

LOGFILE=/home/home/terasort-runs.log
RESULTDIR=/user/einsamkeid

# Mark start of the loop
echo Testing loop started on `date`

# Mapper containers
for i in 2 4   
do
   # Reducer containers
   for j in 1 2 
   do                 
      # Container memory
      for k in 512 1024 1536 
      do                         
         # Set mapper JVM heap 
         MAP_MB=`echo "($k*0.8)/1" | bc` 

         # Set reducer JVM heap 
         RED_MB=`echo "($k*0.8)/1" | bc` 

	echo "" >> $LOGFILE
	echo "---------------------------------------" >> $LOGFILE
	echo "-               NEW RUN               -" >> $LOGFILE
  	echo "---------------------------------------" >> $LOGFILE
	echo "-Dmapreduce.job.maps=$i" >> $LOGFILE
	echo "-Dmapreduce.map.memory.mb=$k" >> $LOGFILE 
	echo "-Dmapreduce.map.java.opts.max.heap=$MAP_MB" >> $LOGFILE
	echo "-Dmapreduce.job.reduces=$j" >> $LOGFILE
	echo "-Dmapreduce.reduce.java.opts.max.heap=$RED_MB" >> $LOGFILE

        /usr/bin/time -f "TERAGEN time: %E real,%U user,%S sys" -ao $LOGFILE $HADOOP_PATH/hadoop jar $HADOOP_MR/hadoop-examples.jar teragen \
                     -Dmapreduce.job.maps=$i \
                     -Dmapreduce.map.memory.mb=$k \
                     -Dmapreduce.map.java.opts.max.heap=$MAP_MB \
                     100000000 $RESULTDIR/tg-10G-${i}-${j}-${k} 1>tera-${i}_${j}_${k}.out 2>tera_${i}_${j}_${k}.err                       

         /usr/bin/time -f "TERASORT time: %E real,%U user,%S sys" -ao $LOGFILE $HADOOP_PATH/hadoop jar $HADOOP_MR/hadoop-examples.jar terasort \
                     -Dmapreduce.job.maps=$i \
                     -Dmapreduce.job.reduces=$j \
                     -Dmapreduce.map.memory.mb=$k \
                     -Dmapreduce.map.java.opts.max.heap=$MAP_MB \
                     -Dmapreduce.reduce.memory.mb=$k \
                     -Dmapreduce.reduce.java.opts.max.heap=$RED_MB \
                     $RESULTDIR/tg-10G-${i}-${j}-${k} $RESULTDIR/ts-10GB-${i}-${j}-${k} 1>>tera_${i}_${j}_${k}.out 2>>tera_${i}_${j}_${k}.err                         

          $HADOOP_PATH/hadoop fs -rm -r -f -skipTrash $RESULTDIR/tg-10G-${i}-${j}-${k}                         
          $HADOOP_PATH/hadoop fs -rm -r -f -skipTrash $RESULTDIR/ts-10GB-${i}-${j}-${k}                 
      done
   done
done

echo Testing loop ended on `date`
```
