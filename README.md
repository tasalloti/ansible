**Generate an ssh key**

  ssh-keygen -t ed25519 -C "jay default"

Copy the ssh key to the server(s)

  ssh-copy-id -i ~/.ssh/id_ed25519.pub <IP Adderss>

Generate an ssh key that’s going to be specifically used for Ansible

  ssh-keygen -t ed25519 -C "ansible"

Copy the ssh key to the server(s)

  ssh-copy-id -i ~/.ssh/ansible.pub

Use an SSH key to connect to a server

  ssh -i .ssh/<key_name> <IP Address>

To cache the passphrase for our session, we can use the ssh agent

  eval $(ssh-agent)
  ssh-add

  Here’s an alias you can put in your .bashrc, to simplify it

  alias ssha='eval $(ssh-agent) && ssh-add'
