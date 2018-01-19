1、 Modified amcl/amcl_node.cpp
--
     *Line 422: changed topic name
     */amcl_pose -> /amcl_pose_origin

2、Added mobileRobot/amcl2odom.py
-
     # Sub Topics:
          /amcl_pose_origin (geometry_msgs::PoseWithCovarianceStamped)<br>
     # Pub Topics:
          /amclodom (nav_msgs::Odometry)<br>
     # Usage:
          a) Make sure mobileRobot navigation.launch is running.<br>
          b) rosrun mobileRobot amcl2odom.py<br>

3、Added robot_pose_ekf/mobile_ekf.launch
-
     # Sub Topics:
          /amclodom (nav_msgs::Odometry)<br>
          /camera_odom (nav_msgs::Odometry)  //TODO<br>
     # Pub Topics:
          /amcl_pose<br>
     # Usage:
          a) Make sure mobileRobot/amcl2odom.py and robot_localization/orbslam_transform is running<br>
          b) roslaunch robot_pose_ekf mobile_ekf.launch<br>
