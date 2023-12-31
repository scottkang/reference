# SpringToolSuite

## github login with ssh key

```bash
$>ssh-keygen -t ed25519 -C "your_email@example.com"
```
This command generates id_ed25519/id_ed25519.pub key files.
id_ed25519.pub can be registered as a new SSH key and used in terminal console. But it cannot be used in SpringToolSuite.

This error message is returned while trying to pull/push operations.
trying ssh-rsa key ~/.ssh/id_rsa with signature type rsa-sha2-512

It seems STS tries to connect to github with id_rsa(256) file but github responds with rsa(512) algorithm. 

I generated a new private/public key with this command, and registered the key to github. And STS could connect to github.
```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
