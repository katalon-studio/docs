---
title: "Katalon OnPremise License Server" 
sidebar: katalon_studio_docs_sidebar
permalink: katalon-studio/docs/license-server.html
description: 
---
Katalon OnPremise License Server is designed to be installed at a location that is accessible from a customer’s network, and be configured with licenses obtained from Katalon.

> The OnPremise license server is provided with the volume subscriptions for Enterprise customers to activate Katalon Studio offline and can be acquired by contacting [Katalon Sales team](mailto:business@katalon.com).


## Features
- Install and set up on your machine privately (within your internal network). [Learn more](https://docs.katalon.com/katalon-studio/docs/license-server.html#install-and-setup-a-server)

- Manage users & organizations. [Learn more](https://docs.katalon.com/katalon-studio/docs/license-server.html#create-an-organization)

- Manage licenses. [Learn more](https://docs.katalon.com/katalon-studio/docs/license-management.html)

- Manage accounts (login, change & reset password). [Learn more](https://docs.katalon.com/katalon-studio/docs/license-server.html#reset-and-forget-password)

- Activate Katalon Studio with OnPremise license server. [Learn more](https://docs.katalon.com/katalon-studio/docs/license-server.html#activate-katalon-studio-with-katalon-onpremise-license-server)

## System requirements

<table><thead><tr><th>&nbsp;</th><th>Requirements</th></tr></thead><tbody><tr><th>Operating System</th><td>Windows, Linux (Ubuntu based)</td></tr><tr><th>CPU</th><td> <em>Minimum</em>: 2 GHz or faster 32-bit (x86) or 64-bit (x64) processor</td></tr><tr><th>Memory</th><td><p</p><p><em>Minimum</em>: 8 GB RAM (64-bit)</p><p><em.</p><p></p><p><em</p><p><em></p></td></tr><tr><th>Hard Drive</th><td>At least 40 GB available hard disk space.</td></tr></tbody></table>

## Install and setup an Onpremise License Server

> This tutorial takes Windows as an example. To learn how to setup an OnPremise License Server in Linux (Ubuntu), please refer to [this document](https://docs.katalon.com/katalon-studio/docs/license-server-ubuntu.html).

### Prerequisite

- Download [PostgreSQL Database version 9.6.16](https://www.postgresql.org/download/)
- For integration, Katalon Studio version should be 7.2.2
- Contact [Katalon Sales team](mailto:business@katalon.com) to get the **Katalon license server installer** and a **license file** (.lic file) to activate the license server.


### Install and create a PostgreSQL database

PostgreSQL database is where you manage all data, including Organizations, Teams, and user accounts used in the server. Please first download [PostgreSQL Database version 9.6.16](https://www.postgresql.org/download/).

1. Run the PostgreSQL installer and follow the PostgreSQL Setup Wizard.

- Create a password for the database superuser (postgres)

  <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/ktop-server/3.PNG" width="" height=""> 

- Select the port number the server should listen on

  <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/ktop-server/4.PNG" width="" height=""> 

2. After installation, open **PgAdmin** which starts on your browser.

3. Sign in with the superuser's password.

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/ktop-server/pgadmin.PNG" width="" height=""> 

4. Create a database named kit.

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/ktop-server/kit.PNG" width="" height="">

> Note: You can use the default superuser postgres or create another Login role with the superuser's privileges.

### Install Katalon license server

> Contact [Katalon Sales team](mailto:business@katalon.com) to get the package and license file. We recommend installing the versions that are compatible with your operating system (only Linux and Windows are supported).

1. Run the installer and follow the Setup Wizard.

- **Destination directory** – this is where the license server will be installed in your machine

  <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/ktop-server/5.PNG" width="" height=""> 

- **TCP ports** – these are the HTTP connector and control ports that your license server will run on. You're recommended to use the default ports unless you're running another application on the same port.


- **Database URL** – the JDBC URL for your database.


- **Server URL** - the address of your license server site. Syntax: http://<IPAddress>:<TCPPort>
E.g., http://localhost:8080

The server will start on your browser once the installation completes with the Activate screen.
You will receive a license file which is used to activate the server as below:

  <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/ktop-server/activate.PNG" width="" height="">

2. After activation, you will be asked to create a default account.

3. Sign in using the default account.

Now, you are at the server Dashboard. You can begin with creating a new organization and inviting your members to join.

## Create an Organization

One member of the team can complete these steps to invite all the others to an Organization for working on projects.


1. Open Katalon OnPremise license server URL, for example, http://192.168.37.109:8080 and log into your account.

2. On the home page, click **Create Organization** at the bottom and confirm your action.

> You will be an Owner of the organization that you have created by default.

3. In the **Organization** View, give a name to your Organization. You can also view your Organization ID here.



### Invite Organization Members

**As an Orgnanization Owner/Admin**

> As an Owner/Admin, you can invite others to join your organization.


1. In the **Organization** view, select **Users**.
2. In the **Users** view, select **Invitations**.
3. Invite your members one by one by entering their email addresses. The newly created invitation link is added to the **Pending Activations** table.
4. Copy and send the invitation link to that person.

   > An email with an invitation link attached is sent to the invited email if you have configured [Mail Server](https://docs.katalon.com/katalon-analytics/docs/ktop.html#configure-mail-server).


Users are only added to the Organization once they sign in with the newly created account. You can track the invited persons' actions by observing their activation links.

**As an invited member**

> As an invited member who has been invited by an Owner/Admin, you can join an organization once you accepted an invitation.

1. Click on the invitation link that the Owner/Admin sent to you
2. You are navigated to an OnPremise License Server view where you need to create and confirm a new password for the account registered with your email.


3. Click **Update password**, and you are done with registering your account with an OnPremise License Server.
4. Sign in with the newly created account to start working on Katalon OnPremise License Server.

> Troubleshoot
>
> If you click on the invitation link and encounter this error: "*This link has been used to reset password.*", it means a password is already updated.
>
> If you click on the invitation link and encounter this error: "*Cannot accept the invitation.*", please check and sign out the currently signed in account. Then use the invitation link to sign in with the corresponding account.

You can grant the new members organization roles. [Learn more](https://docs.katalon.com/katalon-analytics/docs/kt-user-role-permission.html).

## Reset and Forget Password

If you would like to change your password, please go to your **Profile** and click **Change Password** on the upper right corner.

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/ktop-setup-org-team-project/update-pw-1.png" width="364" height="">

In case a user forgets the password, they can click on **Forgot your password** in the **Sign-in** window and follow the instructions to update a new one. However, this solution is only available for the Organizations that have configured [Mail Server](https://docs.katalon.com/katalon-analytics/docs/ktop.html#configure-mail-server). For those Organizations without Mail Server configured, we suggest a workaround below.

1. Open **PgAdmin4**

* In Windows: go to **C:\Program Files\PostgreSQL\9.6\pgAdmin 4\bin** and double-click on **PgAdmin4**.

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/ktop-setup-org-team-project/open-pgAdmin.png" width="" height="">

2. **PgAdmin4** starts on your browser
3. Log into the Server by entering the required password of **postgres** superuser for authentication. This password was created during the setup of PostgreSQL earlier.

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/ktop-setup-org-team-project/login-postgre.png" width="" height="">

4. Select the **kit** database, which is owned by the **postgres** superuser.

5. Select **Schemas > public > Tables**

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/ktop-setup-org-team-project/table.png" width="" height="">

6. In Tables, locate and right-click on **user_account** > **Scripts** > **UPDATE Script**

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/ktop-setup-org-team-project/update-script.png" width="" height="">

7. Copy and paste the following command in the **Query Editor** and replace the password and email of the account.

    ```groovy
    UPDATE public.user_account
        SET password='<_password_>', password_encrypted=false
        WHERE email = '<_email_>'
    ```

8. Click on the **Execute** button on the menu bar.

   <img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/ktop-setup-org-team-project/execute.png" width="" height="">

   If a message indicating the query returned successfully shows up, it means you have done updating a new password for the account.

## Activate Katalon Studio with Katalon OnPremise License Server

After downloading Katalon Studio, you need to activate it in the **Katalon Studio Activation** dialog.

1. Enter the required information.

* **Server URL**: the address of your License Server site that you configured.
* **Email and Password**: the account you have registered with License Server.

2. Click **Activate** to connect with and retrieve Organizations from the License Server.
3. Select an Organization you would like to work on in the drop-down list. Click **OK**.

## Configure Mail Server
 
Katalon License Server is designed exclusively for a restricted network environment. You need to configure a mail server to send and receive email notifications of managing users in your organization.

1. Start your license server.
2. Under an Organization, select **Settings** tab.
3. Provide the information for your mail server.
 
![](https://github.com/katalon-studio/docs-images/raw/master/katalon-analytics/docs/kt-op-mail-server/kt-op-mail-server-config.png)
 
* **Host:** the domain name of the mail server.
* **Port:** the port to be used for that server.
* **Username & Password:** the account to authenticate with the server.
* **Protocol:** the protocol to communicate with the mail server.
 
4. Click **Update** to save and apply your configurations.
 
> Note: You can test the configuration by providing a test recipient and click **Send test email**.
