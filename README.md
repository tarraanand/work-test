Vunique Solutions Private Limited – 5 years
Joined at Associate consultant and resigned as consultant.
First salary – 3 lakhs
Last salary – 7 Lakhs

Conduent Services – Oct 2016 to Aug 2018 – Linux Admin 
Merck - Aug 2018 – Dec 2021 – DevOps Engineer.
Wipro – Feb 18 to till today. – DevOps Engineer. 


Totally, I have 5 + years of IT experience in which 3 years into DevOps.
I have started my career as Linux admin (L1), later I got an opportunity to work on DevOps.

In Conduent services, I use to take care of Linux servers to make sure it is up and running. Writing shell script to start and stop the application, and also archive the log file in store in different location, adding user and changing the permissions & ownership of files & folders etc. Patching up the call the L2 and L3 and developers for Priority issues like if the server is down with some exception errors.
Applications: WIC, EBT, ECC

In Merck, I started as an administrator for DevOps tools like Jira, Confluence, Jenkins, Bitbucket. Later I started writing CI/CD pipelines for end-end deployment and I also worked on Terraform to create AWS resources. We created pipelines on java-based projects, terraform, SSIS packages and bitbucket repo creation so on. we are close to 6 people in the team, and we take care of complete CI/CD administration & implementation, using tools like bitbucket/ Jenkins/ Maven/ SonarQube/ Ansible/ Artifactory/ Confluence/ Jira/ Docker/ Kubernetes and terraform so on.
Applications: Website

In UBS, our main responsibility is to maintain the applications Up and running. Creating a Health check dashboard and email alerts. We created a CI/CD pipeline which run every one hour to Monitor the health check.  Deploying the newest version Via RLC tool or manually deploying using shell script. Setting up the new environments like pre-prod and DR in On-premises server which we are calling as Gen-7 or WMAP. We also implemented the Application in Containers for QA environment which we are calling as Gen-6 or EGL.  We also send logs to developers to identify the error. I also trained the new comers like Veera and Sagar about the process. Currently we are setup the env for new application like FP.
So, this is my overall experience.

Setting:
We request the Unix team to create the new server.
then we create the required folder structure to place Vmargs, jar files, config files and scripts to deploy and start the application
We attach the pbrole to the host machine to run as a root user.

Pipelines:
We are using gitlab for CI/CD, the code is placed in gitlab and we have a pipeline which will clone the code from gitlab to gitlab runner and scan the code with sonarqube, and build it with maven and we upload the build code to artifactory.
We deploy the latest version from artifactory to server via RLC or shell script



 
We create most of our pipelines in multibranch pipeline. As per ITCF controls we create two different type of pipelines(prod & non-Prod). 
When ever the non-prod pipeline trigger. it will clone the code from bitbucket to jenkins workspace. Then the code will be scaned and build and deployed after approval to lower env and will do unit & integrated testing and upload the build code to artifactory and in the post action we will clear the workspace. 
When the prod pipeline triggers it will download the build code from Artifactory to jenkins workspace. We will unzip it as we upload to artifactory in the zip format. And deploy the build code to production env.


Centralized Version Control System (CVCS)
•	Uses a central server to store all files and enables team collaboration.
•	The major drawback is, if the central system is down team can’t collaborate
Distributed Version Control System (DVCS) 
DVCS does not rely on the central server and that is why you can perform many operations when you are offline. You can commit changes, create branches, view logs, and perform other operations when you are offline. You require network connection only to publish your changes and take the latest changes.

git init: This command used for Initialized empty Git repository(/.git folder)
git clone: This command is used for cloning the code from remote repo to local.
Add: This command used for adding files to staging area.
Commit: for committing the changes to .git repo from staging area and create commit ID to the changes.
Push: pushing the changes from git repo to remote repo.
Pull: updating the local version from a remote repo.
Fetch: used for the local git to retrieve the latest meta-data info from the remote repo
Status: used for displaying the state of the working directory and the staging area.
Checkout: This command used for creating new branch in local and switch.
Log: This command used for checking the history of the project.
restore: This command is used for undo the changes in file
git restore -- staged file.py 
This command is used for unstage the file.
Git restore file.py
Reset: used for undo local changes(Commit ID in .git) to the Staging area and Working Directory.
git reset HEAD~1 (or) git reset --mixed HEAD~1
git reset --soft HEAD~1
git reset --hard HEAD~2	
Revert: 
git revert commit-ID

A revert will create a new commit from old commit in the local as we cannot delete the commit in remote repo.
Merge: 
git merge branch-name
This command used for combining changes from one branch to another branch.
Stash:
git stash & git stash apply

git stash temporarily draft changes you've made to your working copy so you can work on something else, and then come back and re-apply them later on.
Rebase:
git rebase branch-name

This command creates a linear history (transfers the completed commits) by moving feature branch into master
Fork: 
Making a copy of the repository in the remote. 
Tags:
git tag -a v1.1 -m "my version 1.1"
git push -u origin tag-name
Tagging is generally used to capture a point in history that is used for a marked version release (i.e. v1. ... A tag is like a branch that doesn't change. Unlike branches, tags, after being created, have no further history of commits.
Fork vs clone
When you fork a repository, you create a copy of the original repository (upstream repository) but the repository remains on your GitHub account. Whereas, when you clone a repository, the repository is copied on to your local machine with the help of Git.
Fetch vs pull
git fetch is the command that tells your local git to retrieve the latest meta-data info from the original (yet doesn't do any file transferring. It's more like just checking to see if there are any changes available). git pull on the other hand does that AND brings (copy) those changes from the remote repository.
Clone vs download
When you clone a repo, you make a copy of the complete history of the git repo including the . ... When you download the repo, you just download the source files of the most recent commit of the default branch without the . git folder.
Rebase vs merge
Git rebase and merge both integrate changes from one branch into another. Where they differ is how it's done. Git rebase moves a feature branch into a master. Git merge adds a new commit, preserving the history.
Pull request:
•	A pull request is an event in Git where a user asks a reviewer of a Git repository to review code they want to merge into master branch from feature or release branch. 
•	We create pull request in bitbucket only.
Branching: 
We use for not disturbing the master code. we create develop and feature branches and work on it. 
Artifactory: it used to store binary code. We upload our build code(binary) from Jenkins workspace to Artifactory. We deploy latest binary to prod env. We use Artifactory because we can’t edit the binary before deploying to prod and also a backup. It is a binary code repo. Code saves as new version. It won’t replace.
----------------------------------------------------------------------------------------------------------------
SonarQube: it is used to check code quality, identify the bugs and code smells. It supports many languages like Java, php, python, groovy, etc. Sonar lint will scan the code and the result will be updated in the sonar server. Sonar scanner we will install in the machine or slave to scan the jobs as per maven or gradle.
Sonar gates: 
----------------------------------------------------------------------------------------------------------------
Maven: it is a build tool for java-based projects. We have Goals like clean, install, package etc to build. The output is stored in target folder (.jar or .war file). We ANT and Gradle tools support java. MS build: it is a build tool for .Net
ANT VS MAVEN: 

Maven: It is a framework. It is mainly a project management tool. The maven plugins are reusable.it is self-intelligent tool. ANT: It is mainly a build tool. The ant scripts are not reusable.
Maven Lifecycle: 
which define the order in which the goals are to be executed. 8 phases: 
validate, compile, test, package, integration test, verify, install, Deploy.
POM.XML
--------------------------------------------------------------------------------------------------------------
Jenkins: 
•	It is CI/CD tool, it is open source and web-based tool, where we create pipelines to scan, build, test and deploy continuously.
•	We have many Plugins to integrate with required tools, to build automated workflow.
•	We can pass diff parameters as required to job. We have many parameters like string, choice, Boolean, file, credential etc.
•	We have many types of jobs like freestyle, pipeline, multi-branch pipeline etc.
•	Jenkins Shared library is the concept of having a common pipeline code in the bitbucket that can be used by any number of pipelines just by referencing it. In fact, multiple teams can use the same library for their pipelines.
•	We can run jobs on multiple machines by Nodes. As we work on multiple projects, some projects need to run on some nodes as we create some configuration as per job. (Share work-load and config). We can run nodes using SSH and JNLP. Node can have executors to run multiple jobs.



Configuration of Jira, SonarQube, Artifactory, Bitbucket to Jenkins. 
•	Install SonarQube, Artifactory, Jira Plugins
•	Configure credentials of SonarQube, Artifactory, Jira.
•	Configure in Global tools.
Jenkins Backup: We download THIN Backup plugin and configure as required.
Permissions: Role based and Project based Authorization strategy where we can give view, write and admin permissions.
Syntax: 
pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                // 
            }
        }
        stage('Test') { 
            steps {
                // 
            }
        }
        stage('Deploy') { 
            steps {
                // 
            }
        }
    }
}

Ansible: 
•	it’s a configuration management tool. It works on push configuration.
•	We will have master and slave arch. we will install ansible only in master. We install python on master and slaves. 
•	Master takes cares of Desired state. We write playbooks to update our configuration on slave nodes.
•	To write effective playbook we use concepts like modules, Tasks, Handlers, roles, loops, when condition, notifier etc.
•	Playbook written in YAML lang. 
•	In Inventory we will list the slave nodes.
•	Once Ansible is installed we will get ansible.cfg and hosts files in /etc/ansible.
•	Modules used are like – apt, yum, package, service, system, file, get_url, messaging, notification, source control etc.
•	handlers are typically used to start, reload, restart, and stop services. run only when if the Task contains a “notify” directive
•	Ansible roles allow you to develop reusable automation components
•	Dynamic inventory : download the ec2.py oy ec2.ini file

•	CMD :
1.	Ansible-playbook <YAML>    (run on all hosts defined)
2.	ansible-playbook <YAML> -f 10  (run 10 hosts parallel)
3.	
4.	ansible-playbook -I inventory <YAML>
5.	ansible -m ping all
6.	ansible -I inventory -m ping all
7.	ansible-galaxy init role-name
8.	ansible-galaxy install role-name
9.	ansible-playbook <playbook> --syntax-check
•	Playbook syntax:
---
- name: Verify apache installation
  hosts: webservers
  become: yes
  tasks:
  - name: Ensure apache is at the latest version
    ansible.builtin.yum:
      name: httpd
      state: latest
    when: ansible_facts[‘os_family’] == “Redhat”

  - name: Write the apache config file
    ansible.builtin.template:
      src: /srv/httpd.j2
      dest: /etc/httpd.conf
    notify:
    - Restart apache

  - name: Ensure apache is running
    ansible.builtin.service:
      name: httpd
      state: started

  handlers:
    - name: Restart apache
      ansible.builtin.service:
        name: httpd
        state: restarted
         roles:
            - common
            - webservers

Role Syntax:
.travis.yml
README.md
defaults/
    main.yml
files/
handlers/
    main.yml
meta/
    main.yml
tasks/
    main.yml
templates/
tests/
    inventory
    test.yml
vars/
    main.yml
________________________________________________________________
Docker: it is a container tool. It is designed mostly for micro-services. I have experience in writing Docker file (Create image and upload to Docker hub. So, we can use that image in any container), docker compose, docker swarm and docker volume.                        micro-services: Breaking the monolithic application into small features.
•	Arch: On Host machine we will install Docker application.
Docker Client	Docker Daemon	Docker registry
•	Docker client where we pass the commands in Cli and client talks to daemon.
•	Docker daemon is a service that runs on your host operating system. Which take care of container and executes the commands passed in client.
•	Dockerfiles is a text documents that allow you to build images for Docker.
•	From Baseimage
•	RUN – cmd while building the image.
•	CMD – cmd to execute while container creation.
•	Expose
•	Label
•	Add and Copy (copy from local machine and add from local and internet)

•	Docker volume used for statefull application. So even if the container gets deleted we will have data from which we can create another store with same data.
•	When you use a bind mount, a file or directory on the host machine is mounted into a container. ... By contrast, when you use a volume, a new directory is created within Docker's storage directory on the host machine, and Docker manages that directory's contents.
•	For multiple containers where we can have same port number for that we use port forwarding.
•	Docker network : bridge, overlay, NAT(windows) etc….. two communicate with two different host we can use overlay network. Docker swarm uses overlay.
•	Docker compose we write in yaml file…. Docker compose should install. And file name is docker-compose.yml
Docker compose example:
version: "3.9"  # optional since v1.27.0
services:
  web:
    build: .
    ports:
      - "5000:5000"
    volumes:
      - .:/code
      - logvolume01:/var/log
    links:
      - redis
  redis:
    image: redis
volumes:
  logvolume01: {}


•	CMD:
1.	docker info
2.	docker ps & docker ps -a
3.	docker image ls
4.	docker image build -t image-name . or file location.
5.	docker container run -itd -name container name -p 8080:8080 jenkins
6.	docker exec containerid
7.	docker container rm container-id
8.	docker image rm image-id
9.	docker volume create volumename
10.	docker volume ls
11.	docker volume inspect
12.	docker run -itd –name Jenkins -v jenkins-volume -p 8080:8080 jenkins/jenkins
13.	docker volume rm volume-name
14.	docker network create - -drive bridge - -subnet 10.1.0.0/16 my-bridge 
15.	docker swarm init  - - advertise-addr private-ip-of-manager-node
16.	docker node ls ----- in Manager node
17.	docker service create  - - replicas 2 –name tomcat tomcat:8
18.	docker service ls
19.	docker service update –image Jenkins
20.	docker-compose –version
21.	docker-compose up -d
22.	docker-compose down
23.	docker-compose config
24.	docker-compose  up -d - -scale web=4 
Kubernetes:
For container deployment which requires automatic scaling, micro services, Volume mounted to EBS and zero downtime deployment.
ARCH: 
 Basic workstyle: create manifests with minimal information which be our desired state. Manifest written in YAML file.
In physical server we need to create master and node but in cloud we have EKS, AKS GKE: master will be provided by default.
Pet vs cattle: K8's run on cattle concept. 
Kubernetes: master will be running only on Linux systems
	           Node can run on windows and Linux system.
 

Object: -
	* Which can save the data and can retrieve...
	* Every object has
		* Object spec: telling the desired state to k8
		* Object status: k8 tells the actual state to user
Specification we will write in yaml file.

Workload: A workload is an application running on Kubernetes. Whether your workload is a single component or several that work together.
		*Pods
		*Controllers

Pod: 	* Pod is a small unit of creation, K8 can’t create containers, it creates pod and pod create containers.
	* Inside the pod we can have one or more docker containers.
	* Volume is attached to pod not to container.
	* Pod gets the network not container.
	* We cannot run same node applications in one node.
	* All container inside the pod will have same network (IP).
	* Good to run one container in one pod.
life cycle of pod: always, restart. etc
status of pod : Pending, running, succeeded, Failed,

Init containers: These are containers which we will execute before the main container. These are supposed to execute for certain time.
: predefined before running the main container.
				init container -1 :
					ping -c 4 google.com
						
				init contianer -2 :
					artifactory.com
					
				Jenkins (Main)
					

Namespace:
 

Controller: controls the workload of objects.
	* Replication controller: we can set no of pods as a desired state
	* Daemon set: create pod on every node in the cluster
	* Stateful sets: we use it when we need storage.
	* Job : which will run some application/script/code which will execute and finish.
	* Cron-job : scheduling the job.

Services: A Service in Kubernetes is an abstraction which defines a logical set of Pods and a policy by which to access them. Services enable a loose coupling between dependent Pods. A Service is defined using YAML (preferred) or JSON, like all Kubernetes objects.

Label: labels that have to be defined whenever a Kubernetes pod is created. Start off small with 3-4 labels per object. Every Kubernetes resource to have application ID, version, owner, stage and release labels.

Deployment: 
	* Replication of pods
	* Pod spec:	
	*strategy.

Storage:
volume
persistent volume: storage class (AWSElasticBlockStore, AzureDisk, GCEPersistentDisk )
persistent volume claim.

Volume : volume lifetime is equal to pod lifetime.
Persistent volume : the lifetime is equal to liftime of cluster.
persistent volume claim: 
storage class: 

Networking : 

Container network : 
pod to pod networking
service to pod
pod to service
ingress

Terraform: I have experience in writing for AWS cloud infrastructure. We write code with the help of resources and data source blocks. We have many other concepts like providers, locals, modules, backend etc to write effective terraform code….
Topics:
Provider, Credentials, Resource, Data source, Arguments, Attributes, Variables, filters, user data, Locals, Look up, mapping, Modules, backend, statefile & lock.


Cloud computing: means Delivery of IT resource over internet with pay as you use model. We take resources for rent. We have many providers like AWS, Azure, GCP.

EC2 instance: it is Virtual Machine where we can run applications.  Instance are created by AMI (Machine image)
S3 (simple storage service): Amazon S3 is an object storage service that stores data as objects within buckets. An object is a file and any metadata that describes the file. object storage with industry-leading scalability, data availability, security, and performance.
VPC: it is a virtual private cloud which make us to launch AWS resources into a virtual network that we defined. VPC create on regions. Subnet is created on AZ.
IAM: Identity access management. This service is globally located not region specific. With IAM we specify who can access which services in AWS. We can grant access in the form of users/groups/policies/roles.
Lambda: it is a serverless compute service that runs our code in response to events.
Cloud watch:
EKS:
ECS:
