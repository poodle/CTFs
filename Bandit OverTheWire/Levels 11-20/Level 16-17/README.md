# Level 16 to 17

## Level Goal
> The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

## Comments
Very similar to the previous level, except now using an MD5 hash.

Code Used
------
```bash
nmap localhost -p 31000-32000
openssl s_client -connect localhost:31790
*bandit16 password*
mkdir -v /tmp/notansshkey
cd /tmp/notansshkey
vi sshkey.private
ssh -i sshkey.private bandit17@localhost
chmod 400 sshkey.private
ssh -i sshkey.private bandit17@localhost
```
