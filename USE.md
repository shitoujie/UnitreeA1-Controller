docker start a1_unitree_gazebo_docker
docker attach a1_unitree_gazebo_docker

roslaunch unitree_gazebo normal.launch rname:=a1 wname:=stairs_single 

docker exec -it a1_unitree_gazebo_docker bash

rosrun unitree_controller unitree_servo 
rosrun unitree_controller unitree_move_kinetic 


ssh root@localhost -p2233
roslaunch a1_cpp a1_ctrl.launch type:=gazebo solver_type:=mpc

rosrun joy joy_node
