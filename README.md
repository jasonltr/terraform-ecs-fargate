Source code for a [tutorial on Medium](https://medium.com/@bradford_hamilton/deploying-containers-on-amazons-ecs-using-fargate-and-terraform-part-2-2e6f6a3a957f) I recently published.

Terraform config for deploying docker containers to ECS using Fargate launch type. Currently set up for my [Crystal Blockchain Application](https://github.com/bradford-hamilton/crystal-blockchain).

### Show your support

Give a ⭐ if this project was helpful in any way!


## Steps

ECS > Get Started

Container name: crystal-blockchain-container

Image: bradfordhamilton/crystal_blockchain:latest

Advanced container configuration: 1024

Storage and logging: awslogs-group value to /ecs/crystal-blockchain-task

So this is the container that I want to deploy

Task definition name: crystal-blockchain-task

Task Memory: 2GB

Task CPU: 1vCPU(1024)

Click Next

Load balancer type: Application Load Balancer

Next

Cluster name: crystal-blockchain-cluster

Review everything, click create

This will take some time

once created view service

Check configure service auto scaling

create policy 
step scaling
policy name: crystal-blockchain-scale-up
create new alarm
alarm name: crystal-blockchain-CPU-high

step scaling
policy name: crystal-blockchain-scale-down
create new alarm
alarm name: crystal-blockchain-CPU-low