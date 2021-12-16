# home-lab

Home server setup.


## Node Setup

Follow these steps to prepare the nodes you want to configure.

### Enable root ssh

1. Login to your server as root.
2. As the root user, edit the sshd_config file found in /etc/ssh/sshd_config:

```sh
sudo vim /etc/ssh/sshd_config
```

3. Add the following line to the file, you can add it anywhere but it’s good practice to find the block about authentication and add it there. You can use `yes` instead of `prohibit-password` if you want to allow ssh'ing to the root user with a password instead of an ssh key.

```
PermitRootLogin prohibit-password
```

4. Save and exit the file.
5. Restart the SSH server:

```sh
sudo systemctl restart sshd
```

6. Create the authorized keys file at `/root/.ssh/authorized_keys`
7. Copy the contents of [ssh/authorized_keys](./ssh/authorized_keys) to the new authorized keys file on your server.


## References

- [Docker containers with Systemd and Ansible](https://kmh.prasil.info/posts/docker-containers-with-systemd-and-ansible/)
- [GitHub plexinc/pms-docker](https://github.com/plexinc/pms-docker)
- Ansible Plugins
  - [List of Builtins](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/index.html#plugin-index)
  - [file](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/file_module.html#ansible-collections-ansible-builtin-file-module)
- [Linux Directory Structure and Important File Paths Explained](https://www.tecmint.com/linux-directory-structure-and-important-files-paths-explained/)
- Plex Docker Images
  - [binhex/arch-plex](https://hub.docker.com/r/binhex/arch-plex)
  - [plexinc/pms-docker](https://hub.docker.com/r/plexinc/pms-docker/)
  - [linuxserver/docker-plex](https://github.com/linuxserver/docker-plex)
