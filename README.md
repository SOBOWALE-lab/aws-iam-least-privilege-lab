[README.md.txt](https://github.com/user-attachments/files/33158973/README.md.txt)
<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Cloud Security with AWS IAM.md

**Project Link:** [View Project](https://nextwork.ai/projects/51a5fd24-7458-58a6-8653-9b90119a0e4a)

**Author:** Sobowale Hafiz  
**Email:** akanjisobowale@gmail.com

---

![Image](https://nextwork.ai/relieved_maroon_noble_fairy/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_1c864649)

## Introducing Today's Project!

### Project overview

In this project, I will demonstrate a interest in cloud security... I'm doing this project to learn basic SOC analyst role



### Tools and concepts

Services I used were Amazon EC2 and AWS IAM Key concepts I learnt include IAM users policies , user groups and account alias.

### Project reflection

This project took me approximately two hours today including project demo time. The most challenging part was understanding the IAM policy since it was written JSON. It was most rewarding for me to see permission denied when the intern tried to delete the production instance. My IAM access is working.

## Tags

### What I did in this step

In this step, I will laucnh two EC2 instances because wa need to boost Nextwork's computing power - we're expecting more users and traffic into our websites over the summer break! 

### Understanding tags

Tags are digiatal labels that you attach to your cloud resources like virtual servers, storage buckes or databases.


### My tag configuration

The tag I’ve used on my EC2 instances is called Env. The value I’ve assigned for my instances are production for my production instance and development for my development instance.


![Image](https://nextwork.ai/relieved_maroon_noble_fairy/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_2e0e5a5d)

## IAM Policies

### What I did in this step

In this step, I will Imagine your company has just hired a new engineering intern. We want them to be able to test their code and manage our development environment, but we absolutely do not want them to touch the live, production environment. If they accidentally stop a production server, it could take down the services that real customers are using!



### Understanding IAM policies

 IAM policy is a rule for who can do what with your AWS resources. It's all about giving permissions to IAM users, groups, or roles, saying what they can or can't do on certain resources, and when those rules kick in.

### The policy I set up

For this project, I’ve set up a policy using JSON

### Policy effect

I’ve created a policy that allows the policy holder that is the intern to have permission to do anything they want to any instance tag with development. 

### Understanding Effect, Action, and Resource

The Effect, Action, and Resource attributes of a JSON policy means wheather or not the policy is allowing or denying action which is effect the policy holder can or can not do.

## My JSON Policy

![Image](https://nextwork.ai/relieved_maroon_noble_fairy/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_1c864649)

## Account Alias

### What I did in this step

In this step, I will set up an alias because it makes login easier.

### Understanding account aliases

An account alias is simply a nickname for our AWS account instead of a long account account ID. W e can now referrence account alias instead.

### Setting up my account alias

Creating an account alias took me 50 seconds. A simple configuration in the acctount dashboard. 
Now, my new AWS console sign-in URL uses the alias instead of my account ID.

![Image](https://nextwork.ai/relieved_maroon_noble_fairy/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_0eb4439b)

## IAM Users and User Groups

### What I did in this step

In this step, I will set up two resources, IAM users and IAM groups. This is because IAM users are like logins for those those users who want access to our AWS account while users group are like foldder to manage users to manage with same level of accsess.

### Understanding user groups

IAM user groups are like folders that collect IAM users so that you can apply permission settings at yhe gtroup level.


### Attaching policies to user groups

I attached the policy I created to this user group, which means any users created in this user group will automatically get the permission attached to our NextworkDevEnvironmentPolicy IAM Policy.

### Understanding IAM users

IAM users are people or entities that can access or login to my AWS account.

## Logging in as an IAM User

### Sharing sign-in details

The first way is the email sign in instruction to the user, while the second way is download a csv. file with the sign in details inside.

### Observations from the IAM user dashboard

Once I logged in as my IAM user, I noticed my user is already denied access to panel on the main AWS console dashboard.  This was because we only set up permission to development EC2 instances, so the intern wouldn't have access to even see anything else.

![Image](https://nextwork.ai/relieved_maroon_noble_fairy/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_6f2ab446)

## Testing IAM Policies

### What I did in this step

In this step, I will login into my AWS account as the intern and test access into the production and development instances because i want to make sure the intern doesn't have the ability to do anything that can affect my production environment.

### Testing policy actions

I tested my JSON IAM policy by attempting to stop the development and production instances.

### Stopping the production instance

When I tried to stop the production instance I was met with an error. This was because my production instance is tagged with the 'production' label which is outside of the scope of our permission policy- interns are only allowed to do things with the development instances.
 

![Image](https://nextwork.ai/relieved_maroon_noble_fairy/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_0e7a9d6a)

### Stopping the development instance

Next, when I tried to stop the development instances i successfully saw the instances changed to stopping and the the stopped. This was because my permission policy allows the intern (i.e users in the Nextwork-dev-group) to stop instances.

![Image](https://nextwork.ai/relieved_maroon_noble_fairy/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_1811801c)

## IAM Policy Simulator

To extend my project, I'm going to set my permission policies in a safer and more controlled way - a tool called the AIM policy simulator. I'm doing this because having to stop instance and log into AWS accounts as other users is a bit distruptive. Let's find a more efficient way.

### Understanding the IAM Policy Simulator

The IAM Policy Simulator is a tool that let us simulate actions and test permisssion settings by defining a specific user/group/role and the action we ant to test for. It's useful for saving time when testing permission testing! no more logging into another user or stopping resources 

### How I used the simulator

I set up a simulation for whether our dev user group has permission to stop instances or delete Tags. The results were denied for both I had to adjust the scope of the EC2 instances to ones that tagged "development" once i apply the tag permission was allowed.

![Image](https://nextwork.ai/relieved_maroon_noble_fairy/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_069d8a621)

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/51a5fd24-7458-58a6-8653-9b90119a0e4a)*

