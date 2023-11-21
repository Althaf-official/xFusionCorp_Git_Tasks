### The Nautilus development team started with new project development. They have created different Git repositories to manage respective project's source code. One of the repositories /opt/games.git was created recently. The team has given us a sample index.html file that is currently present on jump host under /tmp directory. The repository has been cloned at /usr/src/kodekloudrepos on storage server in Stratos DC.



Copy sample index.html file from jump host to storage server under cloned repository at /usr/src/kodekloudrepos/games, further add/commit the file and push to the master branch.

```ruby
thor@jump_host ~$ sudo scp /tmp/index.html  natasha@ststor01:/tmp
```
The command you provided is an `scp` (Secure Copy Protocol) command that is often used to securely copy files or directories between two different machines over a network. Let's break down the command:

1. **`sudo`**: This is a command used to execute another command with superuser privileges. It is often used to perform administrative tasks, and it allows a user to execute a command as a superuser or another user, depending on the configuration.

2. **`scp`**: This is the command for securely copying files between hosts. It's used to transfer files or directories from one machine to another using the SSH (Secure Shell) protocol. `scp` provides encryption and security during the file transfer.

3. **`/tmp/index.html`**: This is the source file you want to copy. In this case, it's the `index.html` file located in the `/tmp` directory of the local machine.

4. **`natasha@ststor01`**: This part specifies the destination machine and the user you want to copy the file to. In this case, you are copying the file to a machine named `ststor01`, and you are specifying the user `natasha` to perform the transfer.

5. **`:/tmp`**: This part specifies the destination path on the remote machine. You want to copy the `index.html` file to the `/tmp` directory on the remote machine `ststor01`.

Putting it all together, the command is asking the system to use `sudo` to execute `scp`, copying the `index.html` file from the local machine's `/tmp` directory to the `/tmp` directory on the remote machine `ststor01`, with the user `natasha` on the remote machine. This command will prompt for authentication on the remote machine, and if successful, it will securely copy the file to the specified location.

```ruby
The authenticity of host 'ststor01 (172.16.238.15)' can't be established.
ECDSA key fingerprint is SHA256:+n1DI5DESdsFlAHiIXfkh9FnLYnhRTa6A4bF/sF5Aew.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'ststor01,172.16.238.15' (ECDSA) to the list of known hosts.
natasha@ststor01's password: 
index.html                                                                          100%   27   110.2KB/s   00:00    
thor@jump_host ~$ ssh natasha@ststor01
The authenticity of host 'ststor01 (172.16.238.15)' can't be established.
ECDSA key fingerprint is SHA256:+n1DI5DESdsFlAHiIXfkh9FnLYnhRTa6A4bF/sF5Aew.
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

[root@ststor01 ~]# cd /usr/src/kodekloudrepos/games


[root@ststor01 games]# ls
info.txt  welcome.txt
[root@ststor01 games]# cat welcome.txt 
Welcome to Nautilus Group
[root@ststor01 games]# cat info.txt 
Welcome to xFusionCorp Industries


[root@ststor01 games]# cp /tmp/index.html  .
[root@ststor01 games]# ls
index.html  info.txt  welcome.txt
```
The command `cp /tmp/index.html .` is used to copy a file from one location to another. Here's an explanation of the command:

- `cp`: This is the command in Unix-like operating systems (including Linux) used to copy files and directories.

- `/tmp/index.html`: This is the source file you want to copy. In this case, it's the `index.html` file located in the `/tmp` directory. The full path to the source file is specified.

- `.`: This represents the destination directory. In Unix-like systems, a single dot `.` refers to the current directory where the command is being executed. So, when you use `.` as the destination, it means you want to copy the source file to the current directory.

So, when you run the command `cp /tmp/index.html .`, it copies the `index.html` file from the `/tmp` directory to the current directory where the command is being executed. This can be useful if you want to move or duplicate a file within the same directory or if you want to copy a file from a different location to your current working directory.


```ruby
[root@ststor01 games]# git add index.html
[root@ststor01 games]# git commit -m "added index.html"
[master 15b2a39] added index.html
 1 file changed, 1 insertion(+)
 create mode 100644 index.html
[root@ststor01 games]# git push -u origin master
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 36 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 330 bytes | 330.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To /opt/games.git
   4ee774a..15b2a39  master -> master
branch 'master' set up to track 'origin/master'.
[root@ststor01 games]# 
```
