Update port to 90: /opt/atlassian/jira/conf/server.xml




usermod -aG sudo jira


Method 3: Editing /etc/passwd file
Edit /etc/passwd for the particular user. Change the user's UID and GID to '0'. This will give root permissions to user.

root:x:0:0:root:/root:/bin/bash



https://linoxide.com/usr-mgmt/give-normal-user-root-privileges/

