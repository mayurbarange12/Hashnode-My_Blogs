---
title: "Day 34 - AWS IAM: Users groups, Users, Roles, Policies, Identity providers and MFA"
datePublished: Sat Jan 20 2024 06:18:18 GMT+0000 (Coordinated Universal Time)
cuid: clrlohrgf000008l55qlehnah
slug: day-34-aws-iam-users-groups-users-roles-policies-identity-providers-and-mfa
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1705727622541/64befece-3966-4a99-9f93-3f2de126f11d.png
tags: trainwithshubham-tws-devops-devopscommunity-shubhamlondhe-automation-awswithtws-7daysofaws-iam-mfa-usergroups-users-roles-policies-identityproviders

---

# **IAM(Identity Access Management)**

IAM (Identity and Access Management) in AWS is a service that enables secure management of user identities and permissions, allowing you to control access to AWS resources. It helps ensure proper authentication and authorization for users and applications interacting with AWS services.

* Search **IAM** in AWS console.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705727979793/5885ca5a-a788-483d-ae15-9c8957048d1c.png align="center")

**<mark>User groups</mark>**

IAM user groups in AWS allow you to collectively **manage** and **assign permissions** to a **set of users**, streamlining **access control**.

**<mark>Users</mark>**

IAM users in AWS are entities with associated **credentials** and **permissions**, allowing **secure access** to and management of AWS resources.

**<mark>Roles</mark>**

IAM roles in AWS provide a way to grant **permissions** dynamically to entities such as users, services, or resources without the need for long-term **credentials**.

**<mark>Policies</mark>**

IAM policies in AWS define **permissions** for users, roles, or groups, specifying allowed actions on AWS resources.

**<mark>Identity Providers</mark>**

IAM Identity Providers in AWS facilitate **external authentication** systems integration for centralized user access control and single sign-on. (**Ex**: If we want to give access to **Github** or another cloud provider **Azure**)

* Click on **Users --&gt; Create user --&gt; User name - Rohit --&gt; Next**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705728044902/9a93e700-eab4-4ef1-a6d4-b018e2d1c547.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705728045809/50d8358e-b7c8-473b-92ae-220a797368ad.png align="center")

* If we want to give AWS Console access to IAM User(**Rohit**) --&gt; Select **Provide user access to the AWS Management Console - optional**
    
* Select **I want to create an IAM user**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705728067553/dbb02e46-0210-42bf-840b-ef47f35e5f34.png align="center")

* Console password --&gt; Select **Autogenerated password**
    
* Select **Users must create a new password at next sign-in - Recommended**
    
* Click on **Next.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705728086943/bfe7b814-7ca3-402f-a332-54231294c4e5.png align="center")

* Select **Attach policies directly**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705728110036/6af41be4-8d09-43cd-a3dc-fe44fff9dfc2.png align="center")

* Search **AmazonS3FullAccess**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705728123382/0aa52fb7-0f65-417b-bd03-e509a4880696.png align="center")

* Select **AmazonEC2FullAccess**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705728135082/d24d0d6c-fb80-4305-8f94-5427a22596f3.png align="center")

* Select **IAMFullAccess**
    
* Select **IAMUserChangePassword**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705728155669/7f807c6f-e27a-42a7-b528-757499c2ca3f.png align="center")

* Click on **Next**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705728178203/60c0a0fd-ed74-4a3e-ab94-87e55271273f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705728182309/8e5a3926-83bf-4f00-9738-083757684c26.png align="center")

* **Tags --&gt; Add new tag**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705728419151/95874d8c-236a-4eee-a19f-948a44cd2a2d.png align="center")

* Key -  **usertype**
    
* Value **\- devops**
    
* Click on **Create user**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705728442642/1278672e-a452-4f1f-bcdd-bd4e7a9950a0.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705728449932/dece7ac5-e2ea-40de-9f8d-1a3fc24bff00.png align="center")

* Click on **Download .csv file**
    
* Click on **Email sign-in instructions**  --&gt; If we want to send mail to anyone who wants to login in IAM user account so that is basically instructions to login in IAM user.
    
* Copy **Console sign-in URL -** [**https://iamdevopsmayur.signin.aws.amazon.com/console**](https://iamdevopsmayur.signin.aws.amazon.com/console) and paste it in other browser.
    
* Account ID (12 digits) or account alias - \*\*\*\*\*\*\*\*\*\*\*\*
    
* IAM user name - **Rohit**
    
* Password - \*\*\*\*\*\*\*
    
* Click on **Sign in**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705728517871/3cd77d23-1a48-4320-92c2-6d940a607b47.png align="center")

* Old password - \*\*\*\*\*\*
    
* New password - \*\*\*\*\*\*
    
* Retype new password - \*\*\*\*\*\*
    
* Click on **Confirm password change**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705728555292/40a53eec-fe9c-431b-a650-e96bc852bbc0.png align="center")

* If we search inside IAM user(Rohit)  **S3   --&gt;** IAM user(Rohit) has access to **S3** service.
    
* If we search inside IAM user(Rohit) **EC2  --&gt;** IAM user(Rohit) has access to **EC2** service.
    
* If we search inside IAM user(Rohit) **RDS --&gt;** Click on **Create database**  --&gt; IAM user(Rohit) has no access to **RDS** service.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705728797218/4aef8c5f-2d7e-4e6f-82ab-59c064e4cc4e.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705728800445/421bf42f-d85e-4a1a-871e-38069c5f6cd6.png align="center")

* Click on **Identity providers**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705729190660/3fd8ecd1-5954-477e-86e3-7ce148737099.png align="center")

* Click on **Add provider**
    
* Provider type **\- SAML** and **OpenID Connect**
    
* Mention **Provider name** In **SAML  --&gt; Add provider**
    
* Mention **Provider URL** in **OpenID Connect --&gt; Add provider**
    
* Now we don't give access to external authentication providers.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705729821811/fc863641-93ec-41d6-854f-d5712c1bed29.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705729825995/efbea8e3-d14e-4e5e-b7b2-9098631cd27d.png align="center")

**<mark>Roles</mark>:  EC2** service and **S3** service can communicate with each other that is called service **Roles**.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705730086231/cf9c5c12-209b-4832-bf21-8bc54e3be3a6.png align="center")

* Click on **Roles**
    
* Click on **Create role**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705730109913/277e5e7f-0cc1-487c-a0f3-daaebb5d6eb3.png align="center")

* Select **AWS service**
    
* Service or use case --&gt; **EC2**
    
* Click on **Next**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705730380354/043dd7d2-ed37-43df-b0bc-419b56d81b0e.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705730385665/e20ca2e8-345e-44db-900a-5a1af2b6edfd.png align="center")

* Search and select **AmazonRDSFullAccess**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705730458553/a38a8b23-625f-4c98-876c-8fb7818c5813.png align="center")

* Click on **Next**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705730485519/08fa9ae5-b578-4125-ba2d-ef33341c85f4.png align="center")

* Role name **\- ec2-rds-role**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705730517909/c90d6c3c-77b2-4ba4-a1a1-0328a9e693e6.png align="center")

* Click on **Create role**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705730543071/c8a4f7e6-ac46-449b-aeaa-2db70fe4cc46.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705730550393/ef21b53f-e11e-4046-958b-62d1adfa6b6e.png align="center")

## **<mark>How to set MFA(Multi-Factor Authentication) to users?</mark>**

* **IAM** --&gt; **Dashboard** --&gt; **Security best practices in IAM --&gt;** Require multi-factor authentication (MFA)
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705730678715/6c04a24a-95bb-47e9-a110-55d8e9c6d176.png align="center")

* Click on **Users --&gt; Rohit  --&gt; Security credentials --&gt; Multi-factor authentication (MFA) --&gt; Assign MFA device**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705730729381/82d04908-ad37-4b60-9f38-b44e593ef5bf.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705730740297/13b19a0a-d1dd-4483-a8d6-fa2de04e1d6b.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705730769416/01382c6f-7d0b-4345-a59c-565b70f57a06.png align="center")

* Install **Google Authenticator** App in mobile phone.
    
* Device name - **Rohit-phone**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705730789683/9e8f2a21-e3a1-4e4f-9f95-9401ba93ddf9.png align="center")

* MFA device: Select any one **Authenticator app/Security Key/Hardware TOTP token** (We selected the Authenticator app)
    
* Click on **Next**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705730806462/fbdad7f2-22b7-4451-92cc-37126633224f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705730837132/8471eac8-9a81-4c12-9ef4-9a0033bbdf1a.png align="center")

* In mobile phone open Google Authenticator App and click on "**+**" icon and click on **Scan a QR code**.
    
* Now in your AWS Console click on **Show QR code.**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705731116676/038516de-a5bd-44d2-818a-aabf63d79707.png align="center")

* After successful scanning the QR code in mobile App it will shows **6 digit numbers**.
    
* Enter that Numbers in **MFA code 1** wait for some time it will shows MFA code 2.
    
* Enter that Numbers in **MFA code 2**.
    
* Click on **Add MFA**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705731128776/820d4ef5-d69d-450e-8e50-deb7987cb568.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705731133407/c631b5fb-5bbd-4a0c-869e-53e9df902bb7.png align="center")

**<mark>What is the Purpose of MFA?</mark>**

* If we logout from **IAM user** (**Rohit)**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705731188288/33408231-65d8-4a3e-b01a-4ab80b8f55c2.png align="center")

* Re Login it to **IAM User(Rohit)**
    
* It will ask **MFA code** check it in the Google Authenticator app enter and Submit it.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705731242650/803c72c3-7306-4674-9667-9ec405ac3ce7.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705731248163/4ee28788-4d7f-4ef5-b10e-d0c232fac364.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1705731252564/8aeea0b0-31df-4e05-b661-98fc9ab07143.png align="center")

* Now IAM Users can log in to the AWS Console.