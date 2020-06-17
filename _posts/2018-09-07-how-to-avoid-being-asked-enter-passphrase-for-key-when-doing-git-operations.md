---
title: How to avoid being asked "Enter passphrase for key ..." when doing git operations
---

- Start the ssh-agent in the background.

```
$ eval "$(ssh-agent -s)"
Agent pid 78736
```

- If you're using macOS Sierra 10.12.2 or later, you will need to modify your `~/.ssh/config` file to automatically load keys into the ssh-agent and store passphrases in your keychain.

```
Host *
 AddKeysToAgent yes
 UseKeychain yes
 IdentityFile ~/.ssh/id_rsa
```

- Add your SSH private key to the ssh-agent and store your passphrase in the keychain.

```
$ ssh-add -K ~/.ssh/id_rsa
```

- And now you can try to connect to your git server.

```
$ ssh git.example.com
```

> Maybe you should change `~/.ssh/id_rsa` to your private key file.

You can find more details on this page : [Adding ssh key to the ssh-agent](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)
