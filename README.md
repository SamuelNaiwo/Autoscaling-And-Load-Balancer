# Autoscaling & Load Balancer

![Alt text](img/ASG%20&%20LB.png)

## Load Balancer
- Receive traffic from internet and send to ec2 instance. When instance is unhealthy, will divert traffic to another instance that Is available.

## Autoscaling
- Delete and terminates broken instances and replaces with a fresh one. Status code 200 set to load balancer.

## Target Groups
- Load Balancer needs Target Groups with required ports which manages the access.

# Launch App In ASG (Auto Scaling Group)

## Launch Template

1. Click Launch template on the left hand side.

2. Click Create a new launch template.

3. Name your template to your requirement. Best practice to name what it is for. I used `samuel-tech221-launch-template-app`

4. Description for version I used `samuel-tech221-launch-template-app-0.1`

5. Select your AMI of your choice. I chose Ubuntu=bionic-18.

6. Choose intance type of your choice. I chose `t2.micro`

7. Choose your key pair if you have one already. I went with `tech221`

8. Choose your security group for your requirements. We needed port 80 and 3000 open.

9. In Advance Details, scroll down to user data and add your script to automate the tasks.

10. Launch your template.

## Auto Scaling Groups

1. On the left menu bar scroll down to auto scaling and click auto scaling groups.

2. Click create auto scaling group.

3. Name your auto scaling group. I went with `samuel_tech221_app_asg`

4. Select your launch template your created

5. Click next

6. Select the required VPC.

7. Select your required AZ (Availability Zones). I went with: `eu-west-1a, eu-west-1b, -eu-west-1c`.

8. Click next.

9. Select attach to a new load balancer.

10. Select Aplication Load Balancer

11. Select internet-facing

12. Create a target group

13. SelectDon’t attach VPC

14. Turn on elastic Load balancing

15. Click next

16. Choose your desired group size. I went with 2.

17. Choose your minimum group size. I went with 2.

18. Choose your maximum group size. I went with 3.

19. Select target scaling policy

20. Select your Metric Type. I went with (Average CPU utilization)

21. Set your target to your requirement. I went with 50 for testing.

22. Instances need 300

23. I would set notification if on client site, but for this test we skipped.

24. Click add tag.

25. Set the Key to `Name` and Value to `samuel-tech221-asg-alb-app`

26. Review everthing and click create auto scaling group.
