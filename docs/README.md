##Chaos Framework

Chaos Engineering is a method of experimentation on infrastructure that brings systematic weaknesses to light. It can be thought of as a learning paradigm to explore the nitty-gritty issues that could potentially lower the throughput of a system.

##How does Chaos Engineering Work?
 It works by doing experimentation our environments to find critical vulnerabilities in the whole system before they make the entire system unusable for the customers. Many tools used for adding Chaos Engineering practices.It catches all vulnerabilities and allows devs to inject failures into their services and prevent them from becoming large outages which can affect business. Chaos Engineering is a type of Preventive Medicine for Infra. In our case we tried to use Chaos cli

##Installation and Getting Started
 1) Build the Dockerfile - It is build on the Docker Image top of the Chaos cli, aws driver plugin and the reporting feature enabled
 2) It make use of the experiments we defined in the Chaos Experiments folder
 3) User needs to change the resourse parameter name like RDS,ALB & ASG Name in the rds.json & asg.json file respectievely
 4) Run the Build by making the above changes in the Property file

##Experiments File - Currently below Scenarios has been covered for the Game Day 
 1) ALB Experiment - As part of the experiment chaos cli will be tryig to reach the ALB and if its giving an expected respose it will try to terminate one of the EC2 Instance and check the behaviour
 2) RDS Experiment - As part of the experiment it will be checking the current db status and the it will be bring the rds instance down and then it will try to capture the behaviour of the application
 3) ECS Experiment - As part of the experiment it will trying to stop one of the task and it will help to evaluate the application behavour after the task has been terminated

##How To Use/How To Contribute
Currently the above mentioned scenarios has been covered and if we want to add new scenarios you need create the specific experiment file inside the Chaos experiments folder. After that we need to add the shell files similar to the existing one's.

Currently to use the existing Scenarios just change the Properies file inside the Chaos_config_files with their specific ALB and ASG
 Helpfull documentation can be found on https://docs.chaostoolkit.org/
