# Introduction

## About this Workshop

In this series of labs we will focus on the specific features of Kubernetes to run Microservices.  These labs use a pre-built set of docker images but you can if you did the **Helidon** and **Docker** modules you can use the images you created there if you wish. 

Estimated Workshop time is 2 hours

<details><summary><b>Self guided student - video introduction</b></summary>


This video is an introduction to the Kubernetes labs. Depending on your browser settings it may open in this tab / window or open a new one. Once you've watched it please return to this page to continue the labs.

[![Kubernetes labs Introduction Video](https://img.youtube.com/vi/6Kg-zH6h3Is/0.jpg)](https://youtu.be/6Kg-zH6h3Is "Kubernetes labs introduction video")

---

</details>



### What you are about to create

You are about to create a Kubernetes deployment with two microservices, Storefront and Stockmanager. These are very simple microservcies to show a very small bit of business logic and how to access the Autonomous Transaction Processing database. Once they are running you will look at how Kubernetes delivers high availability, horizontal scaling and rolling upgrades. There will also be the System services of an Ingress controller with associated load balancer and the Kubernetes dashboard 

![](../../../images/kubernetes-labs-what-will-be-built-core-only.png)


### Lab conventions

We have used a few layout tricks to make the reading of this tutorial more intuitive : 
  
In some cases you will need to executing some command on the command line of a terminal window. If this is a command you can just copy directly from the lab is will be in a box with a **Copy** button. For example
  
  ```bash
  <copy>ls -al</copy>
  ```
  
  However in some cases the command can't just be copied and will need to be entered with some modifications. We have **deliberately** chosen not to allow these to be directly copied as we found that some people didn't make the modifications and then of course the command did not work. In those cases the command will be in a box as below, but without a copy button, you will need to enter the command and in this case replace the pod id, the instructions will make it clear the changes that need to be made. For example the following example kubectl command will get the details of a pod, but the actual pod id will need to be replaced with one from your environment :
  
  ```bash
  kubectl describe pod 234kj3g-c6e43-j3h4
  ```

As we cover quite some theoretical concepts, we included pretty verbose explanations.  To make the lab easier to grasp, we placed the longer parts in *Collapsibles*:

<details><summary><b>Click this title to expand!</b></summary>


If you feel you are already pretty familiar with a specific concept, you can just skip it, or read quickly through the text, then re-collapse the text section by re-clicking on the title. 

---

</details>


### Objectives of the core Labs

#### Lab 1: Setup using the all-in-one script

This module shows you how to use the "all-in-one" scripts to setup the environment for your lab in one go. If you are running in a free trial, or have full admin rights to your tenancy **and** are running in your home region this is the preferred approach, just follow the instructions in this module then once completed jump directly to **Lab 2** skipping the remaining setup modules.

If however you are not in a free trial, do not have full admin rights, not in your home region, or need to modify the default choices for some reason then please use the remaining setup modules instead.

#### Lab 2:  Set up the cluster and run your services in Kubernetes

This section covers how to run the docker images in kubenetes, how to use Kubernetes secrets to hold configuration and access information, how to use an ingress to expose your application on a web port. Basically this covers how to make your docker based services run in in a Kubernetes cluster.

We also look at using Helm to install Kubernetes "infrastructure" such as the ingress server

#### Lab 3: Cloud Native availability with Kubernetes

Kubernetes doesn't just provide a platform to run containers in, it also provides a base for many other things including a comprehensive service availability framework which handles monitoring containers and services to see if they are still running, are still alive and are capable of responding to requests.

This lab looks at how to configure and benefit from these availability features.

#### Labs 4A & 4B: Horizontal and Auto Scaling

Kubernetes also supports horizontal scaling of services, enabling multiple instances of a service to run with the load being shared amongst all of them. 

This horizontal scaling lab shows how you can manually control the number of instances.

Horizontal scaling provides you with a manual process to control how many instances of a microservice you have running, but Kubernetes also offers a mechanism to automatically change the number of instances.

This auto scaling labs shows how you can have Kubernetes automatically scale the number of instances for you.

#### Lab 5: Rolling updates

Kubernetes provides support for performing rolling upgrades, ensuring that the service continues running during the upgrade. Built into this are easy ways to reverse a deployment roll out to one of it's previous states.

This lab looks at how this works and how to recover from a failed update

#### Clean Up (Optional) 

Should you wish (or need) to do so this module shows you how to use a script to remove the resources you created in this lab

### Prerequisites

These labs can be run in many different ways, but in all cases you will need access to a Oracle Cloud Tenancy and be signed in to it.

Please look at the instructions in the **Oracle Cloud Free Tier** section for details of how to sign up for a free trial tenancy and how to log into it. If you already have access to a tenancy (you may be in an instructor led lab, or have a pre-existing tenancy) then go direct to Prerequisites Step 2 which covers how to login to the tenancy.


## Learn more about Kubernetes

For links to useful web pages and other information that I found while writing these labs see the further information on Kubernetes section

## Acknowledgements

* **Author** - Tim Graves, Cloud Native Solutions Architect, Oracle EMEA Cloud Native Application Development specialists Team
* **Contributor** - Jan Leemans, Director Business Development, EMEA Divisional Technology
* **Last Updated By** - Tim Graves, August 2023

