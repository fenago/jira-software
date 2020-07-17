
Linking a Bitbucket or GitHub repository with Jira
==================================================

Use the Jira DVCS connector to link a Bitbucket Cloud or GitHub (hosted
or enterprise) account to Jira Software Server. When linked to Jira
Software, branches, commit messages and pull requests are all seamlessly
referenced in Jira Software issues. This allows Jira Software to display
information about your development activity in the corresponding issue.

This page explains how to link a Bitbucket or GitHub account to Jira.

**Make sure you understand how Jira Software connects to your DVCS account**

The Jira DVCS connector links Jira Software Server to an account on a
DVCS hosting service (Bitbucket Cloud, GitHub, or GitHub Enterprise).
For this reason, the connector needs permission from your DVCS account
to access your account data. The connector does this through
an [OAuth](http://oauth.net/) access token.  

You create an OAuth access token in the DVCS (Bitbucket, GitHub, or
GitHub Enterprise). You should create the access token in the account
that owns the repositories you want to link. How you create the token
depends on the DVCS; the values that make up the token are:

![](https://raw.githubusercontent.com/fenago/jira-software/master/integration/4.png)

After you create a key and secret in the DVCS, you go back to Jira
Software. There, you enter the account, the OAuth key, and secret data
into Jira Software.

The connector does not automatically trust the key and secret. It asks
you to authorize the DVCS connection via the key and secret by supplying
Jira Software an account and password combination. Authorizing is the
equivalent of telling the DVCS connector:

*As a Bitbucket account holder, I know this service asking for a
connection with a key and secret. You are free to use them to get to
this account data. *

The *authorizing account* is not necessarily the account that created
the key and secret. The authorizing account *should* have administrative
access on all the repositories to be linked. 

When you link an account through the Jira DVCS connector, the connector
locates all the public and private repositories owned by the account. It
adds a post-commit service to the repository on the DVCS. The
post-commit service is a piece of code that sits on the repository
waiting for users to commit changes. When a commit happens, the
DVCS connector collects the commit message for processing.

On the Jira Software side, the repositories owned by your DVCS account
appear on the **DVCS accounts** page. A team member may create
repositories under their individual Bitbucket account, but assign the
team as the owner. These repositories also appear in Bitbucket under the
list.

Link a DVCS account to Jira Software Server 
-------------------------------------------

When you link a Bitbucket or GitHub account to Jira Software Server, you
create an OAuth access token in the DVCS tool and then add that token to
Jira Software.

You'll need to have administrative rights on both the Jira Software
instance and on the DVCS account you want to link.  

### Step 1. Create an OAuth access token for your DVCS account 

You create the OAuth access token on your DVCS account. If you are
linking repositories for a team, you should generate this token using
the team account. 

Generate the new OAuth token in either Bitbucket, GitHub, or GitHub
Enterprise, depending on which DVCS hosts your repositories. 

#### Generate a new token in Bitbucket 

Log in as a user with administrative rights on the account.

1.  Choose ***avatar* > Bitbucket settings**. 
2.  (Optional) If connecting a team, choose the team from the **Manage**
    dropdown.
3.  Click **OAuth** under 'Access Management'.
4.  Click **Add consumer**.
5.  Enter the following details:

![](https://raw.githubusercontent.com/fenago/jira-software/master/integration/5.png)


6.  Select the following permissions: 

-   **Account: Write**
-   **Repositories: Admin**(but not Repository: Write)
-   **Pull requests: Read**

![List of
permissions.](https://raw.githubusercontent.com/fenago/jira-software/master/integration/Bitbucket_min_DVCS_perms.png "List of permissions.")

Additionally, select the **This is a private consumer** checkbox.

![Private customer check
box.](https://raw.githubusercontent.com/fenago/jira-software/master/integration/image+(9).png "Private customer check box.")

These are the minimum permissions required by the Jira DVCS connector. Selecting additional permissions will have no adverse affects on the
integration.

​7. Click **Save**.

​8. Click the name of your new consumer to see the OAuth **Key** and
**Secret** values.

​9. Keep your browser open to your DVCS and go to the next step.

#### Generate a new token in **GitHub** 

##### Default account:

 - Username: **fenago-jira**
 - Pasword:  **fenago1234**

Log in as a user with administrative rights on the account:

https://github.com/settings/applications/new

1.  Go to *8Settings**
2.  Select **Developer settings** > **OAuth Apps**.
3.  Choose **Register new application**. 
4.  Enter `JIRA DVCS` for the **Application Name**. 
5.  Enter the Jira Software URL for both the **URL** and **Callback URL** fields. Press **Register Application**.

    Make sure you enter the **Jira Software Base URL** (for example,
    [http://jirjs`<update-me>`.eastus.azurecontainer.io](http://jirjs`<update-me>`.eastus.azurecontainer.io)) for
    *both* the **Homepage URL** and **Authorization callback URL**
    fields. *Don't* use the dashboard URL
    ([http://jirjs`<update-me>`.eastus.azurecontainer.iosecure/Dashboard.jspa](http://jirjs`<update-me>`.eastus.azurecontainer.iosecure/Dashboard.jspa)). 

6.  Keep your browser open to your DVCS and go to the next step.

### Step 2. Link the account on Jira Software 

Do the following to complete the link between your DVCS and Jira
Software:

1.  Log in to Jira Software as a user with administrative rights.
2.  From the Jira Software dashboard click the settings icon
    (![](https://raw.githubusercontent.com/fenago/jira-software/master/integration/settings.png)).
3.  Choose **Applications**.
4.  From the **Integrations **section on the left, choose** DVCS
    accounts**.
5.  Click **Link Bitbucket Cloud or GitHub account**.
6.  Choose **Bitbucket Cloud** as your **Host** value.
7.  Enter a **Team or User Account** name.

    For example, if you want to link the account that owns
    the `https://bitbucket.org/fenago-jira/markdowndemo` repository,
    you would enter `fenago-jira` for the **Team or User Account** value.
    Linking the `fenago-jira` account links all of that account's
    repositories, not only the `markdowndemo` repository.

8.  Copy the OAuth **Key** and **Secret** values from your DVCS site
    into the dialog.    GitHub's **Client ID** is equivalent to the OAuth **Key**. And
    the **Client Secret** is equivalent to the OAuth **Secret**. 
9.  Leave the default auto link and smart commits (recommended) as is or
    change them.
     ![Add new account page with sample
    values.](https://raw.githubusercontent.com/fenago/jira-software/master/integration/add_dvcs_act.png "Add new account page with sample values.") 
10. Click **Add**. 

    If you are connecting a GitHub account and get redirected to a blank
    page, see [DVCS connection to GitHub produces blank
    page](https://confluence.atlassian.com/display/ONDEMANDKB/DVCS+connection+to+Github+produces+blank+page).

11. Grant access when prompted:
     ![Confirm access to your account
    pop-up.](https://raw.githubusercontent.com/fenago/jira-software/master/integration/BB_confirm_access.png "Confirm access to your account pop-up.")

The account you just connected and all of its repositories appears in
the 'Managed DVCS Accounts' page. The initial synchronization starts
automatically. 

### Automatic synchronization and temporarily disabling a link 

After you link an account, Jira Software automatically starts looking
for commits that reference issue keys. The summary shows the
synchronization results and errors, if any. A synchronization of commit
data from the DVCS repository to Jira Software can take some time. As
the synchronization progresses, the commits appear in related issues.
You can always enable and disable the linking of repositories with Jira
Software as needed. 

### How the link appears in Bitbucket 

The DVCS Connector does two things:

-   It adds an OAuth consumer to the linked account's list of integrated
    applications. To view the listing in Bitbucket, click your profile
    image and select **Bitbucket settings**. Click** OAuth **in the
    'Access Management' section and you'll see a listing similar to the
    following:
     ![OAuth Integrated applications
    page.](https://raw.githubusercontent.com/fenago/jira-software/master/integration/BB_account-settings_OAuth.png "OAuth Integrated applications page.")
         
-   The DVCS Connector programmatically adds a post-commit service to
    each of the account's repositories. To view this service,
    choose ![](https://raw.githubusercontent.com/fenago/jira-software/master/integration/settings.png) (Settings) on a repository, then
    click **Services**. You'll see a listing similar to the following:
     ![](https://raw.githubusercontent.com/fenago/jira-software/master/integration/BB_repo-settings_webhooks.png) 
    The DVCS Connector uses its link to check for new repositories on
    the account, then adds this service to those as well. You see the
    result of all this on the 'Services' page.

Example of how commit information appears in a Jira Software project 
--------------------------------------------------------------------

When a developer makes a commit, they should add a Jira Software issue
key to the commit message, like this:

``` {.language-none}
hg commit -m "DVCS-2 add a README file to the project."
hg push
```

Jira Software uses the issue key to associate the commit with an issue,
and so the commit can be summarized in the Development panel for the
Jira Software issue:

![Development panel within an
issue.](https://raw.githubusercontent.com/fenago/jira-software/master/integration/JIRA-agile-board-TIS.png "Development panel within an issue.")


Project permissions required

Project users must have the 'View Development Tools' permission to see
commit information in the Development panel in a Jira Software issue. A
Jira Software admin can edit a project's permission schema to grant this
permission. See [Managing project
permissions](https://confluence.atlassian.com/adminjiraserver/managing-project-permissions-938847145.html).

