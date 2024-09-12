Docker Storage, Bind Mounts and Volumes.
```
1. Docker containers use all the resources of host while running, but when containers stop accidently or intentionally, the data saved on the storage wipes out.
thats why in modern days people use volumes or Bind Mounts to secure the data from wiping out.
2. There are 3 scenarios where this volumes or mounts are found useful.
  a. when a container is UP and running, it stores all the files and logon details of user in LOG FILE, but when the container is stopped this logfile gets deleted since it is temporary memory of Host System.
  b. when a backend app is generating yaml files for yesterday today and 10 days before, and if the container goes down, only todays data is passed on to the frontend.
  c. when container is running, it stores the file wherever it wants, we wont know the path where it is storing,
3. Once the concept of Bind Mount was introduced, the mounts can we bound with the path of the directory where we want to store our data.
4. The Persistent Volume job was also the same but it provides better lifecycle and storage across various cloud platform and local disk.
```
