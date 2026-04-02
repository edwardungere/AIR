# User Notes

## Commands

adduser:
-  High level command. Perl script that automatically creates user's home directory, shell, adds to user user group
-  prompts for password and other information
-  Easy setup
  
useradd:
- Low level command. Needs flags to specfiy options such as group, home directory, etc.
- `useradd <username>`: Creates user with username
- `-g`: Adds user to group
- `-m`: Creates home directory
- `-s`: Create shell for the user, /bin/bash or /bin/sh for limited shell
- `-d`: Takes path for home directory

usermod:
- `-aG`: add user to group
- `-d`: Create home directory for user
- `--move-home`: Move current home directory contents to new home directory
- `-l`: Change user's name
- `-L`: Lokcout user
- `-U`: Unlock user account

## Sudo
- Need to be in sudo group in order to run sudo command (sudo user)
- sudoers file

## Groups
- `groupadd`: create a group
- `groups`: list groups of user
- Need to logout for group to take effect
