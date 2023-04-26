# Autoscaling & Load Balancer

![Alt text](img/ASG%20&%20LB.png)

## Load Balancer
- Receive traffic from internet and send to ec2 instance. When instance is unhealthy, will divert traffic to another instance that Is available.

## Autoscaling
- Delete and terminates broken instances and replaces with a fresh one. Status code 200 set to load balancer.

## Target Groups
- Load Balancer needs Target Groups with required ports which manages the access.

## Node App

1. We need a load balancer and to be specific we need an application load balancer which is the seventh of the layer Open Systems Interconnection (OSI) model. The load balancer will handle request and selects a target from the target group rules. We need port 80 and port 3000 open.

2. We need an ASG (Auto Scaling Group) to contain our EC2 instances for automatic scaling. For example a target tracking policy for if an instances CPU goes 50% or above. The ASG will delete the instance and scale out a new one. we also need a minimum and maximum of instances so the infrastructure is fualt tolerant.

3. We need 3 instances and each instance should be in a different AZ (Availabilty Zone). All instance should have port 80 and port 3000 open.