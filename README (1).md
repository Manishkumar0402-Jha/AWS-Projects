<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Cloud Security with AWS IAM

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-security-iam)

**Author:** manishkumar.jha0402@gmail.com  
**Email:** manishkumar.jha0402@gmail.com

---

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-security-iam_1c864649)

---

## Introducing Today's Project!

### Project overview

In this project, I will demonstrate how to use AWS IAM to control access and permission settings in our AWS account. I'm doing this project to learn about cloud security from the absolute foundations - every company thinks about access permissions, and there are even entire jobs called " IAM Engineers" focused on the skills we're about to build today.

### Tools and concepts

Services I used were Amazon EC2 and AWS IAM!  Key concepts I learnt include IAM users, policies, users groups and account aliases. We also learn how to use the Policy Simulator and how JSON policies work. How to launch EC2 instance, how to tag an instance, how to login as another user.

### Project reflection

This project took me approximately 1.5 hours today including project demo time! The most challenging part was understanding IAM policy since it was written in JSON and it contained multiple statements. It was most rewarding to see permission denied when our intern tried to delete our production instance - our IAM access management worked!

---

## Tags

### What I did in this step

In this step, I will launch two EC2 instances because we need to boost NextWork's computing power - we're expecting more users and traffic into our website over the summer break.

### Understanding tags

Tags are organisational tools that lets us label our resources. They are helpful for grouping resources, cost allocation and applying policies for all resources with the same tag.

### My tag configuration

The tag I’ve used on my EC2 instances is called Env, which stands for environment. The value I’ve assigned for my instances are production and development!

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-security-iam_2e0e5a5d)

---

## IAM Policies

### What I did in this step

In this step, I will use IAM policies to control the access level of new NextWork intern because they should have access to the development environment (i.e. the development instance ) but NOT to the prodection environment.

### Understanding IAM policies

IAM Policies are like rules that dtermines who can do what in our AWS account. We're using policies today to control who has access to our production/environment instance.

### The policy I set up

For this project, I’ve set up a policy using JSON.

### Policy effect

I’ve created a policy that allows the policy holder (i.e. the intern) to have the permisision to do anything they want to  any instance tagged with "development". They can also see information for any instance, but they are denied access to deleting/creating tags for any instance as well.

### Understanding Effect, Action, and Resource

The Effect, Action, and Resource attributes of a JSON policy means whether or not the policy is allowing/denying action (i.e. Effects); what the the policy holder can and cannot do (i.e. Action); and the specific AWS resources that the policyrelates to (i.e. Resource)

---

## My JSON Policy

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-security-iam_1c864649)

---

## Account Alias

### What I did in this step

In this step, I will setup an account alias which is like a nickname  for our AWS account's console login. This is because an account alias makes it simpler for our users to login!

### Understanding account aliases

An account alias is simply a nickname for our AWS account! Instead of a long account ID, we can now reference our account alias instead!

### Setting up my account alias

Creating an account alias took me 30 seconds - it's a simple configuration in the IAM dasboard. Now, my new AWS console sign-in URL uses the alias instead of my account ID.

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-security-iam_0eb4439b)

---

## IAM Users and User Groups

### What I did in this step

In this step, I will set up two IAM resources IAm users, and IAM user groups. This is because IAM users are like logins for people that want access to our AWS account, while users groups are like folders to manage users that have the same level of access.

### Understanding user groups

IAM user groups are like folders that collect IAM users so that you can apply permisision settings at the group level.

### Attaching policies to user groups

I attached the policy I created to this user group, which means any user created inside this group will automatically get the permissions attached to our NextWorkDevEnvironmentPolicy IAM Policy.

### Understanding IAM users

IAM users are people or entities that have access/can login to your AWS account.

---

## Logging in as an IAM User

### Sharing sign-in details

The first way is to email sign in instructions to the user, while the second way is to download .csv file with the sign in details inside.

### Observations from the IAM user dashboard

Once I logged in as my IAM user, I noticed that our user is already denied access to panels on the main AWS console dashboard. This was because we only set up permissions to our development EC2 instance, so our intern wouldn't have access to even see anything else.

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-security-iam_6f2ab446)

---

## Testing IAM Policies

### What I did in this step

In this step, I will login to our own AWS account as intern and test access to the production and development instances because we want to make sure our intern doesn't have the ability to do anything that affect our production environment.

### Testing policy actions

I tested my JSON IAM policy by attempting to stop both the development and production instances.

### Stopping the production instance

When I tried to stop the production instance, we were met with an error!  This was because our production instance is tagged with the 'production' label, which is outside the scope of our permission policy - interns are only allowed to do things to development instances.

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-security-iam_0e7a9d6a)

### Stopping the development instance

Next, when I tried to stop the development instance, we successfully saw the instance state change to Stopping and then Stopped. This was because our permission policy allows the intern (i.e.  users in the nextwork-dev-group) to stop instances.

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-security-iam_1811801c)

---

## IAM Policy Simulator

To extend my project, I'm going to test our permission policies in safer and more controlled way - a tool called the IAM Policy Simulator!  I'm doing this because having to stop instances and log into AWS accounts as other user is bit disruptive. Let's find a more efficient way!

### Understanding the IAM Policy Simulator

The IAM Policy Simulator is a tool that lets us simulate actions and test permissions settings by defining a specific user/group/role and the acion we want to test for. It's useful for saving time when testing permission settings! No more logging into another user or actually stopping resources.

### How I used the simulator

I set up a simulation for whether our development user group has permissions to StopInstances or DeleteTags. The results were denied for both - I had to adjust the scope of the EC2 instances to ones that are tagged with ":development". Once we applied that tag, permissions was allowed.

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-security-iam_069d8a621)

---

---
