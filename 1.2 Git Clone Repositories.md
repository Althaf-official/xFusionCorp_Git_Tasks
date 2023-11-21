### DevOps team created a new Git repository last week; however, as of now no team is using it. The Nautilus application development team recently asked for a copy of that repo on Storage server in Stratos DC. Please clone the repo as per details shared below:



The repo that needs to be cloned is /opt/beta.git


Clone this git repository under /usr/src/kodekloudrepos directory. Please do not try to make any changes in the repo.


```ruby

thor@jump_host ~$ ssh natasha@ststor01
The authenticity of host 'ststor01 (172.16.238.15)' can't be established.
ECDSA key fingerprint is SHA256:W/EwFqKS6+zeng3IC2T1uH9ugTz+694O+k3Qc8koXyo.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'ststor01,172.16.238.15' (ECDSA) to the list of known hosts.
natasha@ststor01's password: 
[natasha@ststor01 ~]$ sudo su -

We trust you have received the usual lecture from the local System
Administrator. It usually boils down to these three things:

    #1) Respect the privacy of others.
    #2) Think before you type.
    #3) With great power comes great responsibility.

[sudo] password for natasha: 
[root@ststor01 ~]# cd /usr/src/kodekloudrepos/
[root@ststor01 kodekloudrepos]# git clone /opt/media.git
Cloning into 'media'...
warning: You appear to have cloned an empty repository.
done.
[root@ststor01 kodekloudrepos]# 

```
