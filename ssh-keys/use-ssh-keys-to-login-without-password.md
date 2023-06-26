# How to use ssh-keys

This is about how to log onto a server via ssh without having to use the password every time.

See [this](https://www.youtube.com/watch?v=wSIsJWPhEqE) video for further explanations.

## Creating a ssh-key with ssh-keygen

First, you have to create an ssh-key that can then be copied onto the server in the next step.
For that, use the ssh-keygen tool.

### Optional parameters

- `-t` for the encryption algorithm (e.g. `dsa` | `ecdsa` | `ecdsa-sk` | `ed25519` | `ed25519-sk` | `rsa`)
- `-b` for the bits of the encryption
- `-C` for a comment, that explains the key

```bash
# basic
ssh-keygen

# more specific
ssh-keygen -t rsa -b 4096 -C "your@email.com"
```

After sending the command, you will be asked for a path (leave the default for the `.ssh` folder). After that, a password for the key can be defined (leave empty in order to get passwordless authentication later).

## Copying the ssh-key onto the server

To copy the key you just created, use the command `ssh-copy-id`.

### Required parameters

- `-i` for the **PUBLIC** key (followed by the filename)
- The username and hostname/IP-address of the server you want to copy to

The command could then look like this:

```bash
# Remember to use the public key (*.pub)
ssh-copy-id -i .ssh/id_rsa.pub root@my-server-ip
```
