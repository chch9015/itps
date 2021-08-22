
DNS---Ec2---ReactJS---apis----Ec2--Flask--Database (RDS--mysql)




frontend --repo - appdemo --reactJS
api --repo - apidemo --- flask 


RDS
backup enable
monitoring -Cloudwatch - Dashboard for the RDS --cpu / number of connections / Storage 
alert RDS cpu usage goes more than 5% - email test 
-[ ] Create own repo - 





Taksks 

Create the repos in your branch
- [x] appdemo --main / develop / stage/ preprod / prod - Protected ---index.html
- [x] apidemo --main / develop / stage/ preprod / prod - Protected----helloworld.py- flask

- [x] create the 4 vpcs 
      - [x] dev -10.1 - bastion---rds--jenkins
      - [x] stage -10.2
      - [x] preprod-10.3
      - [x] prod -10.4 - bastion --rds--jenkins
      - [x]  create the dev bastion 
      - [x]  create the jenkins in private 
      - [x]  create the alb separate for the jenkins
      - [x]  create the reactJS and flask api in the private subnet
      - [x]  create the internete load balancer and attach to the reactjs
      - [x]  craete the internal load balancer and attach to the flaskapi
- [ ] vpc peering between dev - stg, dev-preprod
      - [x] do ssh/telnet from dev bastion to dev private environments (jenkins/reactjs/flask/rds)
      - [ ] do ssh/telnet from dev bastion to stage private environments (jenkins/reactjs/flask/rds)
      - [ ] do ssh/telnet from dev bastion to preprod private environments (jenkins/reactjs/flask/rds)


- [ ]  do ssh/telnet from prod bastion to prod private environments (jenkins/reactjs/flask/rds)



day-1
### DEV 
#### Infra
- [x] create the repos - apidemo,appdemo,infrademo (follow the branching strategy)
- [x] Create the vpc for dev : vpc name: dev - 10.1.0.0/16
    * dev-public-subnet-1a , public-subnet-1b
    * dev-private-subnet-1a 
    * dev-data-subnet-1a 
    * dev-igw
    * dev-natgw
    * dev-public-route
    * dev-private-route
    * dev-eip
- [x] create the bastion in :dev-bastion
- [x] create the jenkins :dev-jenkins
- [x] create the react/api : dev-app, dev-api
- [x] create the rds - dev-rds , dbname: dev_api , username: dev_apiuser
- [x] create the 3 alb , 
      * jenkins-alb 
      * app-alb 
      * api-alb --private subnet--internal 



#### CICD:
- [x] - create jenkins pipeline job for the : dev-appdeploy : /opt/app
- [x] create the jenkins pipeline job for the: dev-apideploy : /opt/api

### validatoin:
hello world : dev.domain-name--app
hellowrold.py : ls -ltr /opt/api
test.py : ls -ltr /opt/api








#### Observability:
- [x] Grafana , Prometheus - ec2 - check instances - 3
- [ ] Kibana, ElasticSearch - Ec2 - check kibana url 

- [ ] Create two databases
      * student
      * employee
- [ ] create two tables
      * student_details
      * employee_details
      - insert the values to the tables.at a time 1000 records has to insert ,use query
- [ ] Cloudwatch dasboards
      * how many ec2's are running
      * stop ec2's when ever not required
      * create a alert when ec2's down, mostley at night times
      * create a alert, when your ec2 is using more then 5%

- [x] Store the terraform tfstate file in S3

#### jenkins master and slave

- [ ] Create a jenkin job, running in the slave machine(master and slave)

- [ ] Create a auto scalling for the api server

- [ ] Create a one API for the flask ,to apiserver
      * test the url in the postman application

- [ ] Python with the Json(get the ec2 information like instance id's,instance state)

- [ ] With python get the CSV(Comma Saparated Values)
