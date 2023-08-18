# Using the OCI DevOps service to update and re-deploy an example microservice into the Oracle Kubernetes Environment.

## About this workshop

Estimated Workshop time is 2 hours

### Prerequisites

These labs can be run in many different ways, but in all cases you will need access to a Oracle Cloud Tenancy and be signed in to it.

Please look at the instructions in the **Oracle Cloud Free Tier** section for details of how to sign up for a free trial tenancy and how to log into it. If you already have access to a tenancy (you may be in an instructor led lab, or have a pre-existing tenancy) then go direct to Prerequisites Step 2 which covers how to login to the tenancy.



### Introduction

**Lab conventions**

We have used a few layout tricks to make the reading of this tutorial more intuitive : 

- If you see a "Bullet" sign, this means **you** need to perform some sort of **action**.  For example opening a window and navigating to some point in a file system
  
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

### What you are about to create

This lab shows you how to use the OCI Devops Serive to build a container image for a Kubernetes services from the source code (held in a git repo). Then upload the container and associated YAML files to the repositories. Next you will see how to create a deployment pipeline to apply these updates artifacts to an Oracle Kubernetes Environment cluster. Finally you will see how to connect these two stages and have them automatically triggered by a code update in the git repo.

### Lab conventions

We have used a few layout tricks to make the reading of this tutorial more intuitive : 

- If you see a "Bullet" sign, this means **you** need to perform some sort of **action**.  For example opening a window and navigating to some point in a file system
  
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

### Objectives of each of the labs

#### Lab 1:  Setup using the all-in-one script

This module shows you how to use the "all-in-one" script to setup the environment for your lab in one go. It will create a Oracle Kubernetes Environment cluster for you and least the basic services as well as an initial running version of the microservices you will be using.

It will also configure the security policies and other items that are needed for using the DevOps service.

#### Lab 2: Create your DevOps project

To do devops work you need a DevOps project, this module shows you how to create and configure that.

#### Lab 3: Get the sample code and upload it to a OCI repository

To run a build you need code to actually compile, this module shows you how to download the sample code, create your own OCI Code repository and to transfer the sample code to that.

#### Lab 4: Examine and update the build_spec.yaml file

The build_spec.yaml file is the core of the build process. This module explains the various parts of the build_spec.yaml file, and then shows you how to setup some vault secrets to use within it. The you upload your version of the build_spec.yaml file to the OCI Code Repository

#### Lab 5: Create your DevOps build pipeline

DevOps build pipelines provide an ordered sequence of stages for running abuild and creating the results. This module shows you how to set one up and get it running.

#### Lab 6: Update your build pipeline to output artifacts

Once you have build artifacts in yur build pipeline you need to pass them from the pipeline to registries and image repositories. This module shows you how to add a new stage to your build pipeline to do this transfer.

#### Lab 7: Create the deployment pipeline

Creating artifacts form a build pipeline is good, but even better is having them automatically deployed into the target environments. This module shows you how to create a deployment pipeline to run this process.

#### Lab 8: Test the CICD process and automatic triggers

This final module of the lab shows you how to have your deployment pipeline automatically triggered from the build pipeline, and then lets you test out the process. Lastly you then look at how to have this process triggered automatically when code is pushed into your OCI Code repo.

## Clean Up (Optional)

Should you wish (or need) to do so this module shows you how to use a script to remove the resources you created in this lab

## Learn More : Configure OCI for DevOps

For this lab to reduce the time needed we've scripted the setup of the environment, but if you're interested in learning more then this module will provide more details. It covers creating the dynamic groups, policies and ssh keys you will need to use the DevOps service and to use the git repo.

## Acknowledgements

* **Author** - Tim Graves, Cloud Native Solutions Architect, Oracle EMEA Cloud Native Application Development specialists Team
* **Contributor** - Jan Leemans, Director Business Development, EMEA Divisional Technology
* **Last Updated By** - Tim Graves, August 2023

