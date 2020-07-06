# Security

## Updates

It's important to keep your system up to date. This is mostly just done by running ```sudo apt update``` and then ```sudo apt upgrade```.

## Change Usernames and Passwords

Changing your username and password away from the default is one of the first things you should do to protect your system.

1. Enable the "root" user, using ```sudo passwd root```. Choose a secure password for this "root" user.
2. Log out of the user "pi". ```logout```
3. Log in as root, with the secure password you set.
4. Rename the user pi to your chosen username. ```usermod -l rasp pi```
5. Change the user's home directory to match the new name. ```usermod -m -d /home/rasp rasp```
6. Logout and back in with the new username.
7. Change the password to something more secure. ```passwd```
8. Check that your user still has the correct privileges. ```sudo apt-get update```
9. If there are no errors, then you can disable the root account again. ```sudo passwd -l root```

## Passwordless Login (SSH Keys)

A further level of security is to authenticate using SSH keys rather than passwords. In order to do this, you must generate a key-pair on your local PC, not the Raspberry Pi.

1. Generate the keypair ```ssh-keygen```. When prompted, press ```Enter``` to save it to the default location ```(C:\Users\username\.ssh\id_rsa)```.
2. Now look inside your ```.ssh``` directory: ```ls ~/.ssh```
    1. The ```id_rsa``` file is your private key. **Keep this file secret and safe on your computer**
    2. The ```id_rsa.pub``` file is your public key. This is what you share with your Raspberry Pi.
3. Take a look at your public key ```cat ~/.ssh/id_rsa.pub```
    1. It should look like ```ssh-rsa <LONG STRING OF RANDOM CHARACTERS> user@host```
4. Copy your public key to the Raspberry Pi ```cat ~/.ssh/id_rsa.pub | ssh <USERNAME>@<IP-ADDRESS> 'mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys'```
5. Now try logging in ```ssh rasp@raspberrypi.local``` and you should connect without a password prompt.
