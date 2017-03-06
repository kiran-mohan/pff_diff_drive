#!/usr/bin/env python

# Author: Kiran Mohan

import rospy
from geometry_msgs.msg import Twist


if __name__=="__main__":
    rospy.init_node("drive_in_circles")
    cmd_vel_publisher = rospy.Publisher("cmd_vel",Twist,queue_size=1000)
    rate = rospy.Rate(100)
    cmd_vel = Twist()
    diameter = rospy.get_param('~diameter',1.0)
    ang_vel = 1.0
    cmd_vel.linear.x = diameter/2
    cmd_vel.angular.z = ang_vel
    while not rospy.is_shutdown():
        cmd_vel_publisher.publish(cmd_vel)
        rate.sleep()
