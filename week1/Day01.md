# Day 01 - Basics

## Ansible Task - Insatll Nginx on Server

---

-name Insall Nginx on server
hosts: all
become: yes

taskes: 
    yum:
        name: nginx
        state: present


## Teraform task - create ec2

 
provide "aws"{
    region: "us-east-1"
}

resources "aws_istance" "PrathnexEC2"  {
ami = "ami"-0abcd1234abcd1234"
instance_type = "c5.xlarge"

tags = {
    Name = "Pathnex-EC2"
}
}       


## Kubernetes Task - create Nginx Pot

apiversion: v1
kind: Pod
metadata:
    name: pathnex-pod
spec:
    containers:
        -name: web
        image: nginx:latest
        ports:
            -containerPort: 80

## shell script _ Print Date & Hostname

#!/bin/bash
echo "Date: $(date)"
echo "HostName: $(hostname)"


# Git integartion
## Jenkins Pipeline - checkout Git
You will learn how to checkout a Git repository and list files.


pipeline {
agent any
stages {
        stage('checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Pathnex/sample-java-app.git"
            }
        }
        stage {
            step {
                sh 'ls -la'
            }   
        }
    }
}

## Gitlab ci - checkout git

you will learn to checkout a git repositor in github ci

stages:
    - checkout
git-checkout:
    stages: checkout
    script:
    -git clone https://github.com/Pathnex/sample-java-app.git
    - cd sample-java-app
    ls -la
