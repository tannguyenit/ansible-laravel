### Introduce

The ansible install some service for php-laravel on Debian
* Nginx
* Cerbot
* Redis
* Docker
* Docker-compose
* Mysql8.0

### Requirement

Copy all.yml.example to all.example in `./inventories/dev/group_vars/`

### Update user password
> If don't have mkpasswd, Plese install on your local first
```
mkpasswd -m yescrypt your_desired_password

```
and update user password at `./inventories/dev/group_vars/all.yml`
>

### Install ansilble community
```
ansible-galaxy collection install community.docker
ansible-galaxy collection install community.mysql
```

### Run
```
ansible-playbook -i inventories/dev/hosts playbooks/main.yml
```

Note
```
sudo mkdir /sys/fs/cgroup/systemd

sudo mount -t cgroup -o none,name=systemd cgroup /sys/fs/cgroup/systemd
```