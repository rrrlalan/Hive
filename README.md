# Run Hive in Docker
Check present working Directory in Hive-Server-1

$ ls /opt

$ ls /opt/new_dir

# How to copy data from Host operating system to Docker Container?
Step 01:- Copy you data other then user directory. Eg :- D or E directory and Open terminal in that directory only where you placed your file
Step 02:- Get Your Container Id 
Step 03:- Write docker copy commond like <docker cp file_name container_id:container_path>

  $ docker cp my_file.txt 1a59b790158b:/opt/new_dir/

# Copy Data from Hive Desktop container to HDFS location
Use put commond like this <hadoop fs -put <container path> <hdfs location>>
  
$ hadoop fs -put /opt/new_dir/depart_data.csv /lln/

# Load data from Docker Container into hive table
  Go to hive terminal -> select database
  
  hive> use hive_db;
  
  hive> load data local inpath '/opt/new_dir/depart_data.csv' into table department_data_01;


