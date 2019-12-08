# Ansible Role AWS Cloudwatch Logs Agent

Ansible Role for installing and configuring the CloudWatch Logs Agent

## Role Variables

`awslogs_config`: list of log files to monitor

## Example:
``` Ansible Playbook
awslogs_config:
    - log_stream_name: laravel_app_log
      log_group_name: laravel
      file: /var/www/laravelapp/storage/log/laravel.log
      datetime_format: "%b %d %H:%M:%S"

    - log_stream_name: expressjs_app_log
      log_group_name: expressjs
      file: /var/lib/docker/containers/ffcd36803e1483463a940d21e4278/ffcd36803e1483463a940d21e4278.log
      datetime_format: "%b %d %H:%M:%S"

    - log_stream_name: django_app_log
      log_group_name: django
      file: /var/log/debug.log
      datetime_format: "%b %d %H:%M:%S"
```

## Add to existing Playbook

```Ansible Playbook
- hosts: all
  become: yes
  roles:
    - cloudwatch-logs-agent # Cloudwatch Logs Ansible Role folder name
```

## Author

Created by [Rommel Porras](https://www.rommelporras.com) of [DevOps Cycle](https://www.devopscycle.com/) 

## License

MIT License
