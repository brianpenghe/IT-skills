---
title: '[PUTTY] how to log on to the server with public key/private key'
date: 2015-12-31T11:23:00.002-08:00
draft: false
url: /2015/12/putty-how-to-log-on-to-server-with.html
---

> **Archived note — originally created: 2015-12-31 — very old (8+ years) — likely outdated**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


ref: https://www.digitalocean.com/community/tutorials/how-to-use-ssh-keys-with-putty-on-digitalocean-droplets-windows-users
---------------------------------------------------------------------------------------------------------------------------

Setting Up an SSH Session with SSH Keys in PuTTY
------------------------------------------------

Now that we have a droplet with our public key inside, we can use PuTTY to connect to it. We will do this by setting up and saving a session. This way we will be able to quickly reconnect at a later time with all of our settings saved.

Start by opening up the main PuTTY program. You can do this by double clicking on the PuTTY program, or by tapping the Windows key and typing "PuTTY".

Inside, you'll be taken to the main session screen. The first step is to enter the IP address of your droplet into the session page. You can get this address from your DigitalOcean control panel:

![PuTTY droplet address](https://assets.digitalocean.com/articles/putty_do_keys/enter_ip.png)

By default, SSH happens on port 22, and the "SSH" connection type should be selected. These are the values we want.

Next, we'll need to select the "Data" configuration inside the "Connection" heading in the left-hand navigation menu:

![PuTTY Data section](https://assets.digitalocean.com/articles/putty_do_keys/data_category.png)

Here, we will enter our server's username. For the initial setup, this should be the "root" user, which is the administrative user of your server. This is the account that has been configured with your SSH public key. Enter "root" into the "Auto-login username" prompt:

![PuTTY username](https://assets.digitalocean.com/articles/putty_do_keys/enter_user.png)

Next, we'll need to click on the "SSH" category in the navigation menu:

![PuTTY SSH menu](https://assets.digitalocean.com/articles/putty_do_keys/ssh_category.png)

Within this category, click on the "Auth" sub-category.

There is a field on this screen asking for the "Private key file for authentication". Click on the "Browse" button:

![PuTTY private key](https://assets.digitalocean.com/articles/putty_do_keys/browse_keys.png)

Search for the private key file that you saved. This is the key that ends in ".ppk". Find it and select "Open" in the file window:

![PuTTY find key](https://assets.digitalocean.com/articles/putty_do_keys/open_key.png)

Now, in the navigation menu, we need to return to the "Session" screen that we started at.

This time, we need to create a name for the session that we will be saving. This can be anything, so select something that will help you remember what this is for. When you are finished, click on the "Save" button.

![PuTTY save session](https://assets.digitalocean.com/articles/putty_do_keys/enter_session.png)

You now have saved all of the configuration data needed to connect to your new server.

Connect to Your Server Using the Saved PuTTY Session
----------------------------------------------------

Now that you have your session saved, you can recall these values at any time by returning to the "Session" screen, selecting the session you would like to use in the "Saved Sessions" section, and click "Load" to recall the settings.

This will auto-fill all of the fields with the values you initially selected.

When you are ready to actually connect to your server, on the "Sessions" screen, click the button at the bottom that says "Open" after you have loaded your session:

![PuTTY open connection](https://assets.digitalocean.com/articles/putty_do_keys/open_session.png)

The first time that you connect with the remote host, you will be asked to verify the identity of the remote server. This is expected the first time you connect to a new server, so you can select "Yes" to continue.

![PuTTY verify host](https://assets.digitalocean.com/articles/putty_do_keys/verify_host.png)

Afterwards, you should immediately be logged into your new server without ever having to type in a password:

![PuTTY terminal session](https://assets.digitalocean.com/articles/putty_do_keys/terminal.png)

If you've gotten this far, you've successfully configured SSH keys with DigitalOcean!

Conclusion
----------

You should now be able to easily deploy new DigitalOcean VPS instances with your SSH public key. You can use the SSH keys you created on as many servers as you would like. They are not one-time use configurations.

To learn about [how to embed your PuTTY SSH keys into server instances that you _already_ have up and running](https://www.digitalocean.com/community/articles/how-to-create-ssh-keys-with-putty-to-connect-to-a-vps), follow this guide.

By Justin Ellingwood

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
