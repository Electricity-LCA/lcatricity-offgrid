# Requirements
1. A Raspberry Pi with minimum 1GB RAM. This project was tested on two Raspberry Pi 4b each with 4GB RAM 
2. A 50W or higher solar panel
3. (Optional) A USB or SSD drive to use as the data storage layer for etcd and for any database you wish to run


# Installation setup
1. Install docker, using the [official instructions](https://docs.docker.com/engine/install/debian/)
2. Restart the Raspberry Pi
3. Check that Docker is running e.g. by running the hello-world image
```bash
docker run hello-world
```

1. [Get k3s](https://docs.k3s.io/installation)
2. Enable `cgroups` in the firmware config of your Pi. Open the cmdline file with superuser right
```bash
sudo nano /boot/firmware/cmdline.txt
```
Then append to the end of the line `cgroup_memory=1 cgroup_enable=memory` (the result should be still a file with one line)
3. [Get helm](https://helm.sh/docs/intro/install/)

# Converting a docker-compose to a kubernetes helm chart
Use [Kompose](https://kubernetes.io/docs/tasks/configure-pod-container/translate-compose-kubernetes/)
