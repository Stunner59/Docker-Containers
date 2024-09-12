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

Docker Networks.
```
1. when container is created on host, the container uses host network, known as eth0, when container is created, it has a network Veth0 created by Docker0, Docker0 ensures that the container is connected with the host netowork.
2. But sometimes some containers needs to be isolated from the other containers due to security reasons.
3. Thats why we use custom eth to seperate 1 container from another.
4. There are 3 types of network
   a. Host network
   b. Bridge Network
   c. OverLay Network (K8's and Swarm)
```
Demo
```
1. We create a login page of nginx image using command
   docker run -d -name login nginx:latest
2. we do inspect using
   docker inspect login
3. we can check that IP is from bridge network.
4. Similiar steps for Logout Page
5. For Finance page, we use an isolated network.
   docker run -d -name finance --network secure_network niginx:latest
6. when we inspect the finance, we can see that the subnet is different and if we try to ping the finance container from login we get no output.
   docker exec -it <containe-name> /bin/bash
```
