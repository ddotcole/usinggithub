# Using Github

### About

This repository is a place for describing the process I use to initalize a SSH to Github on my computer as well as basic commands used in my normal work flow.

### Setting up a SSH Connection

Bring up a console and navigate to:

    cd ~/.ssh

Type in the following command to generate a SSH key pair:

    ssh-keygen -t ed25519 -C <email address>
    
Follow all information requested by ssh-keygen.  Once complete, check for a **config** file in **~/.ssh**.  If the **config** does not exist, create a new text file and insert the following information:

    Host git@github.com
      AddKebold codeysToAgent yes
      IdentityFile ~/.ssh/<key file name>
      
Run the following command, copying the output to the clipboard:

    cat <key file name>.pub
    
This is your public key which must be added to Github using the following process:

   * Click on **User** in upper right corner of Github and choose **Settings**
   * Click **SSH and GPG Keys** section on the left hand side
   * Click **New SSH key** pasting the previously copied key into the **Key** section
   * Provide the key with a **Title** and click **Add SSH key**

Now you can test your SSH connection to Github using the following command:

    ssh -T git@github.com

Everything is working fine if you end up with a response like this:

    Hi <user>! You've successfully authenticated, but GitHub does not provide shell access.
