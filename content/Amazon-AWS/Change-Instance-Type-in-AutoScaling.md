+++
date = "2015-07-15T22:17:00+02:00"
draft = false
title = "Change Instance Type in AutoScaling"

[menu.main]
Name = "Change Instance Type"
parent = "Amazon-AWS"
+++


AWS does not allow to edit launch configuration. If you notice, we define instance type at time of launch configuration. So if you want to change instance type in Auto Scaling group than you need to create new launch configuration for that.

Following are the step to edit AutoScaling group.

change-autoscaling-group-instance-type-18
Change AutoScaling Group Instance Type
Note: This does not apply to running instances in this group, To apply it on running instance please terminate old instance. New instance will be create as per defined in launch configuration.

