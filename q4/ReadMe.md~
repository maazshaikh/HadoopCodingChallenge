I have used the Hive tool for this question i.e Q2 in the test.

First using the sqoop I have dumped the database to hdfs.

Then later I created individual tables in hive using the hive sql.

I(Maaz) have used Vishwa's machine to execute the following code, therefore the username is displayed as vishwa.

Case:
Find out CTC of each department grouped by each dept_manager's name and number of employees under the manager. The output should be in the following format: Dept_no, Department, Manager, CTC, total_emps. Please upload the final CSV along with the code and jar files(if any) to your github and provide the link below.

SQOOP
GET all data from MySql and Store it in HDFS

Hive
1. departments => create external table if not exists departments (dept_no String, dept_name String) comment 'department details' row format delimited fields terminated by ',' lines terminated by '\n' stored as textfile;
2. departments => load data inpath 'hdfs:/user/maas/sqoop/departments/part-m-00000' overwrite into table departments;
3. dept_emp => create external table if not exists dept_emp (emp_no int, dept_no String, from_date String, to_date String) COMMENT 'department employees details' row format delimited fields terminated by ',' lines terminated by '\n' stored as textfile;
4. dept_emp => LOAD DATA INPATH 'hdfs:/user/maaz/sqoop/dept_emp/part-m-00000' OVERWRITE INTO TABLE dept_emp;
5. dept_manager => create external table if not exists dept_manager (dept_no String, emp_no int, from_date String, to_date String) COMMENT 'department manager details' row format delimited fields terminated by ',' lines terminated by '\n' stored as textfile;
6. LOAD DATA INPATH 'hdfs:/user/maaz/sqoop/dep_manager/part-m-00000' OVERWRITE INTO TABLE dept_manager;

7. hive -e 'set hive.cli.print.header=true; select d.dept_no as DeptNo, d.dept_name as DepartmentName, e.first_name as ManagerFirstName, e.last_name as ManagerLastName, count(de.emp_no) as TotalEmp, sum(s.salary) as CTC from departments d join dept_manager dm on dm.dept_no = d.dept_no join employees e on e.eid = dm.emp_no join dept_emp de on de.dept_no = d.dept_no join salaries s on s.eid = de.emp_no where de.from_date > dm.from_date and de.to_date <= dm.to_date group by dm.emp_no, d.dept_no, d.dept_name, first_name, last_name;' > /home/vishwa/Desktop/Q4_ans.csv;

SLF4J: Class path contains multiple SLF4J bindings.
SLF4J: Found binding in [jar:file:/usr/local/hive/lib/log4j-slf4j-impl-2.4.1.jar!/org/slf4j/impl/StaticLoggerBinder.class]
SLF4J: Found binding in [jar:file:/usr/local/hadoop/share/hadoop/common/lib/slf4j-log4j12-1.7.5.jar!/org/slf4j/impl/StaticLoggerBinder.class]
SLF4J: See http://www.slf4j.org/codes.html#multiple_bindings for an explanation.
SLF4J: Actual binding is of type [org.apache.logging.slf4j.Log4jLoggerFactory]

Logging initialized using configuration in jar:file:/usr/local/hive/lib/hive-common-2.1.0.jar!/hive-log4j2.properties Async: true
WARNING: Hive-on-MR is deprecated in Hive 2 and may not be available in the future versions. Consider using a different execution engine (i.e. tez, spark) or using Hive 1.X releases.
Query ID = vishwa_20161206021801_179f7d89-9fcf-4911-92f7-4becf6c6e1f3
Total jobs = 8
SLF4J: Class path contains multiple SLF4J bindings.
SLF4J: Found binding in [jar:file:/usr/local/hive/lib/log4j-slf4j-impl-2.4.1.jar!/org/slf4j/impl/StaticLoggerBinder.class]
SLF4J: Found binding in [jar:file:/usr/local/hadoop/share/hadoop/common/lib/slf4j-log4j12-1.7.5.jar!/org/slf4j/impl/StaticLoggerBinder.class]
SLF4J: See http://www.slf4j.org/codes.html#multiple_bindings for an explanation.
SLF4J: Actual binding is of type [org.apache.logging.slf4j.Log4jLoggerFactory]
2016-12-06 02:18:08	Starting to launch local task to process map join;	maximum memory = 477102080
2016-12-06 02:18:09	Dump the side-table for tag: 0 with group count: 9 into file: file:/usr/local/hive/iotmp/daf16359-742e-402c-9e8b-49d809b75747/hive_2016-12-06_02-18-01_128_4329720069656721516-1/-local-10015/HashTable-Stage-15/MapJoin-mapfile40--.hashtable
2016-12-06 02:18:09	Uploaded 1 File to: file:/usr/local/hive/iotmp/daf16359-742e-402c-9e8b-49d809b75747/hive_2016-12-06_02-18-01_128_4329720069656721516-1/-local-10015/HashTable-Stage-15/MapJoin-mapfile40--.hashtable (578 bytes)
2016-12-06 02:18:09	Dump the side-table for tag: 1 with group count: 9 into file: file:/usr/local/hive/iotmp/daf16359-742e-402c-9e8b-49d809b75747/hive_2016-12-06_02-18-01_128_4329720069656721516-1/-local-10015/HashTable-Stage-15/MapJoin-mapfile41--.hashtable
2016-12-06 02:18:09	Uploaded 1 File to: file:/usr/local/hive/iotmp/daf16359-742e-402c-9e8b-49d809b75747/hive_2016-12-06_02-18-01_128_4329720069656721516-1/-local-10015/HashTable-Stage-15/MapJoin-mapfile41--.hashtable (1169 bytes)
2016-12-06 02:18:09	End of local task; Time Taken: 1.06 sec.
Execution completed successfully
MapredLocal task succeeded
Launching Job 1 out of 8
Number of reduce tasks is set to 0 since there's no reduce operator
Job running in-process (local Hadoop)
2016-12-06 02:18:11,672 Stage-15 map = 0%,  reduce = 0%
2016-12-06 02:18:13,679 Stage-15 map = 100%,  reduce = 0%
Ended Job = job_local777348585_0001
Stage-18 is selected by condition resolver.
Stage-19 is filtered out by condition resolver.
Stage-2 is filtered out by condition resolver.
SLF4J: Class path contains multiple SLF4J bindings.
SLF4J: Found binding in [jar:file:/usr/local/hive/lib/log4j-slf4j-impl-2.4.1.jar!/org/slf4j/impl/StaticLoggerBinder.class]
SLF4J: Found binding in [jar:file:/usr/local/hadoop/share/hadoop/common/lib/slf4j-log4j12-1.7.5.jar!/org/slf4j/impl/StaticLoggerBinder.class]
SLF4J: See http://www.slf4j.org/codes.html#multiple_bindings for an explanation.
SLF4J: Actual binding is of type [org.apache.logging.slf4j.Log4jLoggerFactory]
2016-12-06 02:18:18	Starting to launch local task to process map join;	maximum memory = 477102080
2016-12-06 02:18:19	Processing rows:	200000	Hashtable size:	199999	Memory usage:	149077240	percentage:	0.312
2016-12-06 02:18:20	Processing rows:	300000	Hashtable size:	299999	Memory usage:	133504072	percentage:	0.28
2016-12-06 02:18:20	Dump the side-table for tag: 1 with group count: 300024 into file: file:/usr/local/hive/iotmp/daf16359-742e-402c-9e8b-49d809b75747/hive_2016-12-06_02-18-01_128_4329720069656721516-1/-local-10011/HashTable-Stage-12/MapJoin-mapfile21--.hashtable
2016-12-06 02:18:20	Uploaded 1 File to: file:/usr/local/hive/iotmp/daf16359-742e-402c-9e8b-49d809b75747/hive_2016-12-06_02-18-01_128_4329720069656721516-1/-local-10011/HashTable-Stage-12/MapJoin-mapfile21--.hashtable (11210974 bytes)
2016-12-06 02:18:20	End of local task; Time Taken: 2.122 sec.
Execution completed successfully
MapredLocal task succeeded
Launching Job 3 out of 8
Number of reduce tasks is set to 0 since there's no reduce operator
Job running in-process (local Hadoop)
2016-12-06 02:18:22,600 Stage-12 map = 0%,  reduce = 0%
2016-12-06 02:18:26,610 Stage-12 map = 100%,  reduce = 0%
Ended Job = job_local390946570_0002
Stage-16 is filtered out by condition resolver.
Stage-17 is selected by condition resolver.
Stage-3 is filtered out by condition resolver.
SLF4J: Class path contains multiple SLF4J bindings.
SLF4J: Found binding in [jar:file:/usr/local/hive/lib/log4j-slf4j-impl-2.4.1.jar!/org/slf4j/impl/StaticLoggerBinder.class]
SLF4J: Found binding in [jar:file:/usr/local/hadoop/share/hadoop/common/lib/slf4j-log4j12-1.7.5.jar!/org/slf4j/impl/StaticLoggerBinder.class]
SLF4J: See http://www.slf4j.org/codes.html#multiple_bindings for an explanation.
SLF4J: Actual binding is of type [org.apache.logging.slf4j.Log4jLoggerFactory]
2016-12-06 02:18:31	Starting to launch local task to process map join;	maximum memory = 477102080
2016-12-06 02:18:32	Dump the side-table for tag: 0 with group count: 158024 into file: file:/usr/local/hive/iotmp/daf16359-742e-402c-9e8b-49d809b75747/hive_2016-12-06_02-18-01_128_4329720069656721516-1/-local-10009/HashTable-Stage-10/MapJoin-mapfile10--.hashtable
2016-12-06 02:18:32	Uploaded 1 File to: file:/usr/local/hive/iotmp/daf16359-742e-402c-9e8b-49d809b75747/hive_2016-12-06_02-18-01_128_4329720069656721516-1/-local-10009/HashTable-Stage-10/MapJoin-mapfile10--.hashtable (9538399 bytes)
2016-12-06 02:18:32	End of local task; Time Taken: 1.518 sec.
Execution completed successfully
MapredLocal task succeeded
Launching Job 5 out of 8
Number of reduce tasks is set to 0 since there's no reduce operator
Job running in-process (local Hadoop)
2016-12-06 02:18:34,743 Stage-10 map = 0%,  reduce = 0%
2016-12-06 02:18:37,749 Stage-10 map = 100%,  reduce = 0%
Ended Job = job_local11443762_0003
Launching Job 6 out of 8
Number of reduce tasks not specified. Estimated from input data size: 1
In order to change the average load for a reducer (in bytes):
  set hive.exec.reducers.bytes.per.reducer=<number>
In order to limit the maximum number of reducers:
  set hive.exec.reducers.max=<number>
In order to set a constant number of reducers:
  set mapreduce.job.reduces=<number>
Job running in-process (local Hadoop)
2016-12-06 02:18:39,063 Stage-4 map = 100%,  reduce = 100%
Ended Job = job_local1035217197_0004
MapReduce Jobs Launched: 
Stage-Stage-15:  HDFS Read: 11175033 HDFS Write: 0 SUCCESS
Stage-Stage-12:  HDFS Read: 11175033 HDFS Write: 0 SUCCESS
Stage-Stage-10:  HDFS Read: 109956214 HDFS Write: 0 SUCCESS
Stage-Stage-4:  HDFS Read: 219912428 HDFS Write: 0 SUCCESS
Total MapReduce CPU Time Spent: 0 msec
OK
Time taken: 37.965 seconds, Fetched: 24 row(s)
