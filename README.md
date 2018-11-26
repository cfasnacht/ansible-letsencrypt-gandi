# ansible play to manage letsencrypt wildcard certs with gandi

## How to this play:
Add your hosts to the hosts file section [letsencrypt-server]
Add a gandi api key variable to vault file: variable name: vault_letsencrypt_api_key

`ansible-vault create group_vars/vault.yml`

### run it:
`ansible-playbook manage_letsencrypt.yml --diff -C`


## Details:
## generate a staging certificat manually:
certbot certonly -n --manual --manual-auth-hook=/usr/local/sbin/certbot-gandi.sh --preferred-challenges=dns --email=admin@example.com --server https://acme-staging-v02.api.letsencrypt.org/directory --agree-tos --manual-public-ip-logging-ok -d 'example.com'

## revoke a certifice
certbot certonly -n --manual --manual-auth-hook=/usr/local/sbin/certbot-gandi.sh --preferred-challenges=dns --email=admin@example.com --server https://acme-staging-v02.api.letsencrypt.org/directory --agree-tos --manual-public-ip-logging-ok -d 'example.com'
