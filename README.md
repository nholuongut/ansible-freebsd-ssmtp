# freebsd_ssmtp

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>


## Requirements

### Collections

* community.general


## Variables

Review the defaults and examples in vars.


## Workflow

1) Change shell to /bin/sh.

```
shell> ansible mailserver -e 'ansible_shell_type=csh ansible_shell_executable=/bin/csh' -a 'sudo pw usermod freebsd -s /bin/sh'
```

2) Install the role and collections.

```
shell> ansible-galaxy role install nholuong.freebsd_ssmtp
shell> ansible-galaxy collection install community.general
```

3) Fit variables, e.g. in vars/main.yml

```
shell> editor nholuong.freebsd_ssmtp/vars/main.yml
```

4) Create playbook and inventory.

```
shell> cat freebsd_ssmtp.yml

- hosts: mailserver
  roles:
    - nholuong.freebsd_ssmtp
```

```
shell> cat hosts
[mailserver]
<mailserver-ip-or-fqdn>
[mailserver:vars]
ansible_connection=ssh
ansible_user=freebsd
ansible_become=yes
ansible_become_method=sudo
ansible_python_interpreter=/usr/local/bin/python3.7
ansible_perl_interpreter=/usr/local/bin/perl
```

5) Install and configure the mailserver.

```
shell> ansible-playbook freebsd_ssmtp.yml
```

6) Test it

```
shell> echo -n 'Subject: test\n\nTesting ssmtp' | sendmail -v admin@example.com
```


## References

- [FreeBSD handbook: 28.7. Setting Up to Send Only](https://www.freebsd.org/doc/handbook/outgoing-only.html)
- [FreeBSD handbook: 28.4. Changing the Mail Transfer Agent](https://www.freebsd.org/doc/handbook/mail-changingmta.html)
- [ArchLinux SSMTP](https://wiki.archlinux.org/index.php/SSMTP)


# 🚀 I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.🌟
