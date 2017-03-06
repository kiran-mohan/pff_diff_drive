#!/usr/bin/env python

# Author: Kiran Mohan

import rospy
from geometry_msgs.msg import Twist
import math
import time

if __name__=="__main__":
    rospy.init_node("drive_in_squares")
    cmd_vel_publisher = rospy.Publisher("cmd_vel",Twist,queue_size=1000)
    move_cmd_vel = Twist()
    side = rospy.get_param('~side',1.0)
    move_cmd_vel.linear.x = side

    turn_cmd_vel = Twist()
    turn_cmd_vel.angular.z = math.pi/2

    zero_cmd_vel = Twist()
    while not rospy.is_shutdown():
        cmd_vel_publisher.publish(move_cmd_vel)
        time.sleep(1.0)
        cmd_vel_publisher.publish(zero_cmd_vel)
        time.sleep(2.0)
        cmd_vel_publisher.publish(turn_cmd_vel)
        time.sleep(1.0)
        cmd_vel_publisher.publish(zero_cmd_vel)
        time.sleep(2.0)
