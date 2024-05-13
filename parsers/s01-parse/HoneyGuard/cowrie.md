## Cowrie log parsing

Exemple of cowrie log:
2024-05-13T21:54:51.212481Z [HoneyPotSSHTransport,0,56.56.0.100] login attempt [user/password] failed

Log parser:
COWRIE_LOGIN_ATTEMPT: '%{TIMESTAMP_ISO8601:timestamp} \[HoneyPotSSHTransport,%{NUMBER},%{IP:source_ip}\] login attempt \[%{DATA:user}/%{DATA:password}\] %{GREEDYDATA:status}'

This parsing retrieves many info on this log like :
- date
- source ip
- user
- password
- and the status of the login attempt

If the status is failed, it triggers the bruteforce scenario.
