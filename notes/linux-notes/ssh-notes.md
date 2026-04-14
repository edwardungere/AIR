# SSH Notes

## Public Key Generation

ssh-keygen -y -f <private-key.pem>

Public key needs to be located in user's .ssh directory, ssh checks there for corresponding public key to authenticate requests
If needed, user needs to be allowed in /etc/ssh_config file

If password authentication is enabled, SSH falls back to that if no key is specified
