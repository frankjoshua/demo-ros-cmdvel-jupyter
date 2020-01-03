# Quick Start
```
export ROS_IP=192.168.2.66
export ROS_MASTER_URI=http://$ROS_IP:11311
docker run -it \
    --network="host" \
    --env="ROS_IP=$ROS_IP" \
    --env="ROS_MASTER_URI=$ROS_MASTER_URI" \
    frankjoshua/ros-master
```
```
export ROS_IP=192.168.2.66
export ROS_MASTER_URI=http://$ROS_IP:11311
xhost +

docker run -it \
    --network="host" \
    --env="DISPLAY" \
    --env="QT_X11_NO_MITSHM=1" \
    --env="ROS_IP=$ROS_IP" \
    --env="ROS_MASTER_URI=$ROS_MASTER_URI" \
    --volume="/tmp/.X11-unix:/tmp/.X11-unix:rw" \
    frankjoshua/ros-turtlesim
```
```
export ROS_IP=192.168.2.66
export ROS_MASTER_URI=http://$ROS_IP:11311
docker run -it \
    --network="host" \
    --env="ROS_IP=$ROS_IP" \
    --env="ROS_MASTER_URI=$ROS_MASTER_URI" \
    --env="JUPYTER_ENABLE_LAB=true" \
    --mount src="$(pwd)",target=/home/jovyan/work,type=bind \
    -p "8888:8888" \
    frankjoshua/ros-jupyter
```