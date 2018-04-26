# ubuntu-sshd
SSH-able Docker container for test use
https://hub.docker.com/r/kamatama41/ubuntu-sshd/

## How to Use
```sh
$ container_id=$(docker run -d --rm --publish=2222:22 kamatama41/ubuntu-sshd)

# Login via password (It's 'passw0rd')
ssh ubuntu@localhost -p 2222
ubuntu@localhost's password: passw0rd

# Login via keyfile (You can copy the private key from the container)
$ docker cp ${container_id}:/home/ubuntu/.ssh/id_rsa_test . && chmod 400 id_rsa_test
$ ssh ubuntu@localhost -p 2222 -i id_rsa_test
```
