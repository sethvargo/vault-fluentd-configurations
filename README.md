# HashiCorp Vault fluentd configurations

This repository contains a list of common fluentd, syslog, and logrotate
configurations for running HashiCorp Vault.

## Assumptions

There are some assumptions you might need to change based on your Vault setup:

1. Vault server logs go to `/var/log/vault/server.log`.

1. Vault audit logs go to `/var/log/vault/audit.log`.


## Usage

- `fluent` - general fluentd configurations

    ```
    curl -svo /etc/fluentd/config.d/vaultproject.io.conf https://raw.githubusercontent.com/sethvargo/vault-fluentd-configurations/master/fluent.d/vaultproject.io.conf
    systemctl restart fluentd
    ```

- `google-fluentd` - Google (Stackdriver) fluentd configurations

    ```
    curl -svo /etc/google-fluentd/config.d/vaultproject.io.conf https://raw.githubusercontent.com/sethvargo/vault-fluentd-configurations/master/google-fluent.d/vaultproject.io.conf
    systemctl restart googlefluentd
    ```

- `logrotate` - Logrotate configurations

    ```
    curl -svo /etc/logrotate.d/vaultproject.io.conf https://raw.githubusercontent.com/sethvargo/vault-fluentd-configurations/master/logrotate.d/vaultproject.io.conf
    ```

- `rsyslog` - Pull syslog/rsyslog Vault logs into a file

    ```
    curl -svo /etc/rsyslog.d/vaultproject.io.conf https://raw.githubusercontent.com/sethvargo/vault-fluentd-configurations/master/rsyslog.d/vaultproject.io.conf
    systemctl restart rsyslog
    ```
