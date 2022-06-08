## create user

```bash
adduser ilya

adduser ilya sudo
```

need permit root login. change `/etc/ssh/sshd_config`. 

search line `PermitRootLogin yes` and replace `yes` on `no`

restart ssh `systemctl restart ssh`


## create ssh folder 

```bash
mkdir ~/.ssh
```

and past id_rsa.pub

```bash
vi ~/.ssh/authorized_keys
```

```bash
chmod -R 700 ~/.ssh/
```

again go in `/etc/ssh/sshd_config` and change it.

search line `PasswordAuthentication yes` and replace `yes` on `no`

and if you don't want enter password when using sudo. we need:

```bash
sudo visudo
```

replace one `%sudo   ALL=(ALL:ALL) ALL` with  `%sudo   ALL=(ALL:ALL) NOPASSWD:ALL`

and if `www` folder be created with root privileges to need comback right

```bash
sudo chmod -R $USER:$USER /var/www/
```


---

The note was created based on [pepelsbey](https://github.com/pepelsbey/playground/blob/main/56/4-user.md)
