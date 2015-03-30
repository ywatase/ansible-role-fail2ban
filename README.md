fail2ban
===

## How to use

requirements.yml

```
---
- src: https://github.com/ywatase/ansible-role-fail2ban
```

インストール

```
ansible-galaxy install -r requirements.yml -p ./roles
```

site.yml

```
- hosts: web
  roles:
    - role: ansible-role-fail2ban
      fail2ban_jail:
          "nginx-http-auth":
              enabled: "true"
          "ssh-iptables":
              enabled: "true"
          "apache-http-auth":
              enabled: "true"
```

fail2ban_jailの中身が、jail.localに書きだされます。

上の例の場合: jail.local


```
[nginx-http-auth]
enabled = true

[ssh-iptables]
enabled = true

[apache-http-auth]
enabled = true
```

こんな感じになります。
