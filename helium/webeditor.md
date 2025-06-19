# WebEditor

To use Helium's Web Editor, you will need to allocate an extra port to your server. If you are using Pterodactyl, navigate to your Admin panel.

Once there, click servers, then your navigate to your server, and go into the Build Configuration tab.

Now, add an extra allocation to your server.

**If you do not have Administrator access to your host, you may need to request an additional port.**

Then in Helium `/modules/webeditor.yml`, change the port and domain to what you specified in your Pterodactyl Panel.
