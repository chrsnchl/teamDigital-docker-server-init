adduser chris
usermod -aG sudo chris
ufw app list
ufw allow OpenSSH
ufw enable
ufw status

# in a new tab, so you dont lose active root session...
ssh chris@your_server_ip

# concern: dont use passwords for login, use public SSH keys 
# ssh-keygen -t rsa 
# copy the root SSH key, for the user to use:
rsync --archive --chown=chris:chris ~/.ssh /home/chris
