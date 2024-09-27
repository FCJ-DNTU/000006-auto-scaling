---
title: "Deploying FCJ Management with Auto Scaling Group"
date: "`r Sys.Date()`"
weight: 1
chapter: false
---

# Deploying FCJ Management Application with Auto Scaling Group

## Overview

In this exercise, we will deploy the application with an Auto Scaling Group to ensure the scalability of the application according to user needs. Additionally, we will implement a Load Balancer to distribute the load and manage user access requests to our Application Tier.

Make sure to review the [Deploying FCJ Management Application on a Windows/AmazonLinux Virtual Machine] document and understand how to deploy the application on the virtual machine. We will utilize the virtual machine deployed for **FCJ Management** for large-scale deployment and scaling within the Auto Scaling Group.

## Auto Scaling Group

An **Auto Scaling Group** is a collection of EC2 Instances. This group has the ability to automatically adjust the number of EC2 Instance members based on the configured scaling policy.

## Launch Template

A **Launch Template** is a feature that allows you to create a template for initializing EC2 Instances. This simplifies and streamlines the process of creating EC2 Instances for use with the Auto Scaling service.

## Load Balancer

A **Load Balancer** is a tool that distributes incoming data traffic to AWS resources, specifically EC2 Instances in this lab, within a designated Target Group.

## Target Group

A **Target Group** is a set of AWS resource elements that receive data traffic routed by the Load Balancer.

![Auto Scaling Group](/images/2-Prerequiste/0.png?featherlight=false&width=50pc)

## Contents

1. [Introduction](1-introduction/)
2. [Preparation](2-preparation/)
3. [Create Launch Template](3-create-launch-template/)
4. [Setup Load Balancer](4-setup-load-balancer/)
5. [Test](5-test/)
6. [Create Auto Scaling Group](6-create-auto-scaling-group/)
7. [Test Solutions](7-test-solutions/)
8. [Clean up Resources](8-cleanup/)
