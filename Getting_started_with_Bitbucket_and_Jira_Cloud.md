
Getting started with Bitbucket and Jira Cloud
=============================================


#### Overview

**Before you begin...**

- Step 1. Sign up for Bitbucket and create a Bitbucket team
- Create a Bitbucket account
- Create a team
- Create a team
- Step 2. Invite team members to your team on Bitbucket
- Step 3. Create repositories in or move repositories to your Bitbucket account
- Step 4. Connect the team account in Jira
- Make sure you understand how Jira connects to your Bitbucket account
- Procedure to link an account
- Automatic synchronization and temporarily disabling a link
- How the link appears in Bitbucket

Learn how you can connect the Bitbucket code hosting service with Jira
Cloud.  Connecting Bitbucket to Jira gives your team the power to see
commits, branches, pull requests. You can also create branches and see
the status of pull requests all from the  development panel in Jira or
Jira Agile.

![Development panel within an
issue.](https://raw.githubusercontent.com/fenago/jira-software/master/integration/dev_panel.png "Development panel within an issue.")

You won't see the builds reference shown in the screenshot above unless
you[Integrate Jira with
Bamboo](https://confluence.atlassian.com/x/EQQ_EQ).

Before you begin... 
-------------------

1.  Bitbucket and Jira Cloud are independent services: you will have
    both a Jira Cloud account and a Bitbucket team each with their own
    set of users, permissions, and access rules.

2.  Bitbucket teams are not accounts: they must be managed by an
    administrator (or administrators) who have individual Bitbucket
    accounts. However, the Bitbucket team can have its own payment
    plan. 

3.  Every member of the Bitbucket team must have their own individual
    Bitbucket account. When you invite new team members using their
    email they are also automatically invited to sign up for Bitbucket
    and are automatically added to your team when they complete sign
    up.  
4.  You can transfer Bitbucket [repository ownership to a
    team](https://confluence.atlassian.com/x/bYFIEQ): this can be
    helpful if you want to create a team based upon existing
    repositories.

Step 1. Sign up for Bitbucket and create a Bitbucket team 
---------------------------------------------------------

### Create a Bitbucket account 

If you already have an account, you can skip this section and go to
the [next](https://confluence.atlassian.com/adminjiraserver/getting-started-with-bitbucket-and-jira-cloud-938846891.html#GettingstartedwithBitbucketandJiraCloud-create-bb-team).
When you create a Bitbucket individual account you must supply the
following fields:

![](https://raw.githubusercontent.com/fenago/jira-software/master/integration/1.png)


To sign up for a Bitbucket account:

1.  Open [https://bitbucket.org/account/signup/](https://bitbucket.org/account/signup/) in
    your browser.
2.  Complete the fields in the sign up form.
3.  Click **Sign up**.

When you are done signing in, Bitbucket places you in
the **Dashboard **of your account. Take a second to look around the user
interface. Across the side of each Bitbucket page is a series of options
that let you navigate around Bitbucket. On the top bar is a link
for **Teams**. **Select Teams** > **Create team** and move to the next
section.

### Create a team 

To better understand how teams work let’s first take a look at how they
fit into the Bitbucket environment.

![](https://raw.githubusercontent.com/fenago/jira-software/master/integration/2.png)

Create a team 
-------------

The following process and infographic describe how to create a very
simple team consisting of you, one member, and one repository. Feel free
to follow along in your Bitbucket account, or just read through to get
an idea of what goes into creating a team.

![](https://raw.githubusercontent.com/fenago/jira-software/master/integration/3.png)


Step 2. Invite team members to your team on Bitbucket 
-----------------------------------------------------

You can add team members to your linked Bitbucket team account. These
may be the same users you added to Jira.  It is your choice. Users that
you add to Bitbucket need not have accounts on the Jira instance.

 To add a user to a team, you add the user to one of the team's groups,
as follows:

1.  Log in to Bitbucket as a user with administrative rights on the
    team.
2.  Choose Your avatar > **View all teams**.
3.  Choose the team you want to add new members to.
4.  Choose **Settings** > **User groups**.
5.  Click on the group you want to add the user to.
6.  Enter the user's username or email address, then click **Add**:

    ![](https://raw.githubusercontent.com/fenago/jira-software/master/integration/bitbucket_add_user_to_group.png)
    
    If you entered an email address that corresponds to a Bitbucket
    account, Bitbucket resolves the account for you. If Bitbucket can't
    resolve the address, it sends the user an invitation to create a
    Bitbucket account and join the team.

Step 3. Create repositories in or move repositories to your Bitbucket account 
-----------------------------------------------------------------------------

A repository (sometimes called a repo) contains your project code. 

Whether you have no files or many files, you'll first want to create a
repository on Bitbucket Cloud. From there, you can clone your repository
to your local system and start working on it.

If you name a repository with upper case letters, you'll see the name
with upper case letters in Bitbucket, but Bitbucket converts the name to
all lower case in the repository UR. As a result, you can't create two
repositories with names that result in the same URL.

#### To create a repository 

1.  Click **+** in the global sidebar and
    select **Repository** under **Create a new**.
2.  Choose a repository **Workspace**. 
3.  Select a project from the **Project** dropdown menu. If a project
    does not exist, click on **Create new project** at the bottom of
    the **Project** dropdown menu to create a new project in which to
    work and collaborate with others on your repository.
4.  Enter a **Repository name** that will describe your repository and
    appear in its URL.
5.  Keep access to your repository set to **Private** unless you want to
    make your repository public so that anyone can see it.
6.  If you already have files that you want to add to your repository,
    select **No** from **Include a README?** Otherwise, go with the
    default option or select a one of the included README options.
7.  Select the **Version control system**. If you don't know the
    difference, keep **Git** as the default system.
8.  Click **Create**.



#### After you create a repository 

What comes next depends on what you want to do with your repository:

-   **Starting from scratch with no files?** — Clone the repository to
    your local system to connect Bitbucket repository to a local
    directory. [Learn
    how](https://confluence.atlassian.com/bitbucket/clone-a-repository-223217891.html)
-   **Working on existing files that aren't under version
    control?** — Add unversioned files to a repository before pushing
    them to Bitbucket. [Learn
    how](https://confluence.atlassian.com/bitbucket/add-unversioned-code-to-a-repository-877177133.html)
-   **Already have local files in a Git or Mercurial
    repository?** — Push versioned code to an empty repository,
    maintaining commit history. [Learn
    how](https://confluence.atlassian.com/bitbucket/push-versioned-code-to-an-empty-repository-877177145.html)

Take a minute to explore what comes with your new repository.

The Bitbucket service allows you to create an unlimited number of public
repositories.  The number of private repositories is restricted by your
plan.

#### Tips, Tricks, and Links to More Information

-   You can transfer a Bitbucket repository from an individual Bitbucket account to your Jira team account.
-   You can import a Git or Mercurial project from your local system into Bitbucket.

Step 4. Connect the team account in Jira 
----------------------------------------

### Make sure you understand how Jira connects to your Bitbucket account 

The connector needs permission from your Bitbucket account to access
your account data. The connector does this through
an [OAuth](http://oauth.net/) access token.  

You create an OAuth access token from the Bitbucket account. You should
create the access token on the team that owns the repositories that you
want to link.  The values that make up the token are:

  --------------------- ---------------------------------------------
  key                   A string generated by the Bitbucket system.
  secret                A string generated by the Bitbucket system.
  authorizing account   The account that authorizes the token.
  --------------------- ---------------------------------------------

After you create a key and secret in Bitbucket, go back to Jira. There,
you can enter the account, the OAuth key, and secret data.

Bitbucket does not automatically trust the key and secret it will ask
you to authorize the Bitbucket connection.

When you link your Bitbucket account with Jira all the public and
private repositories owned by the account. It adds a POST commit hook
service to the repository on the Bitbucket system.  The POST commit hook
is a piece of code that sits on the repository waiting for users to
commit changes.

On the Jira Cloud side, the repositories owned by your Bitbucket account
appear on the **Manage DVCS Accounts** page. A team member may create
repositories under their individual Bitbucket account, but assign the
team as the owner. These repositories also appear in Bitbucket under the
list.

### Procedure to link an account 

It is a two step procedure to link a Bitbucket account to Jira. To work
through this procedure, you must have administrative rights on both the
Jira Cloud instance and on the Bitbucket account you want to link.  

#### Step 1. Create an OAuth access token for your Bitbucket account 

To link a Bitbucket account you create an OAuth access token on your
Bitbucket account.   If you are linking repositories under a team, you
should generate this token under the team account.   

Log in to Bitbucket as a user with administrative rights on the account.

1.  Choose **Manage account**. 
2.  (Optional) If connecting a team, choose the team from
    the **Account** drop-down.
3.  Select **OAuth**.
4.  Click **Add consumer**.
5.  Enter `Jira DVCS` for the **Name**.
6.  Leave the other fields fields blank.
7.  Press **Add consumer**.

Keep your browser open to Bitbucket  and go onto the next step.

#### Step 2. Link the account on Jira 

To complete the link between your DVCS and Jira:

1.  Log in to Jira Cloud as a user with administrative rights.
2.  From the Jira dashboard click the settings icon ![](https://raw.githubusercontent.com/fenago/jira-software/master/integration/settings.png)

3.  Choose **Applications** then **DVCS accounts** (under 'Integrations'
    in the left-hand panel).
4.  Click **Link a Bitbucket Cloud or GitHub account**.
5.  Choose **Bitbucket Cloud** as your **Host** value.
6.  Enter a **Team or User Account**.

    For example, if you want to link the account that owns
    the `https://bitbucket.org/fenago-jira/markdowndemo` repository then you
    would enter `fenago-jira` for the **Team or User Account** value.
     Linking the `fenago-jira` account links all of that account's
    repositories, not only the `markdowndemo` repository.

7.  Copy the **OAuth Key** and **OAuth Secret** from your Bitbucket
    account into the dialog.
8.  Leave the default auto link and smart commits (recommended) as is or
    change them.
    ![Add new account dialog with sample
    values.](https://raw.githubusercontent.com/fenago/jira-software/master/integration/add_dvcs_act.png "Add new account dialog with sample values.")
9.  Click **Add**. 
10. Grant access when prompted by the system:

![Confirm access to your account pop-up.](https://raw.githubusercontent.com/fenago/jira-software/master/integration/grantaccess.png "Confirm access to your account pop-up.")

11. Upon success, the **DVCS accounts** page displays with your
    account. 

The account you just connected and all of its repositories appear in
the **DVCS accounts **page. The initial synchronization starts
automatically.  After that, the system continues to sync your repository
automatically on a regular basis.

### Automatic synchronization and temporarily disabling a link 

After you link an account, Jira automatically starts looking for commits
that reference existing issue keys. The summary shows the
synchronization results and errors, if any. A synchronization of commit
data from the DVCS repository to Jira can take some time. As the
synchronization progresses, the commits appear in related issues. You
can always enable and disable the linking of repositories with Jira as
needed. 

### How the link appears in Bitbucket 

The DVCS Connector does two things:

-   It adds an OAuth consumer to the linked account's list of integrated
    applications. To view the listing in Bitbucket, click your profile
    image and select **Manage Account**. Click **Integrated
    applications** and you'll see a listing similar to the following:

    ![Integrated applications page with a sample OAuth
    consumer.](https://raw.githubusercontent.com/fenago/jira-software/master/integration/oath_consumer.png "Integrated applications page with a sample OAuth consumer.")
-   The DVCS Connector programmatically adds a POST commit hook service
    to each of the account's repositories.  To view this service,
    choose Settings 
        
        ![](https://raw.githubusercontent.com/fenago/jira-software/master/integration/settings(1).png)
    
    then click **Hooks** to display the Hooks page. You'll see a listing
    similar to the following:

    ![Hooks page with a sample POST
    service.](https://raw.githubusercontent.com/fenago/jira-software/master/integration/tutorial-hooks-sidexpand.png "Hooks page with a sample POST service.")
    The DVCS Connector uses its link to check for new repositories on
    the account, then adds this service to those as well. You see the
    result of all this on the **Services** page.

