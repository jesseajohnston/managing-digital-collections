---
title:  "Interacting with a LAMP Server"
---

This section describes how to find and interact with a LAMP server.
UMSI provides each student in SI 676 with their own server, which is
already configured with a LINUX operarating system, the Apache web server software,
and the capacity to work with PHP files and SQL databases.
As you work to get your servers running Omeka S, you need to get the software files,
add them to your server, and configure them to run on your server.

# Find Your Server

Each student in the class has a server provided by UMSI.
Your server can be accessed at a URL formulated with the following pattern,
where `YOUR-UNIQNAME` is substituted with your actual uniqname:

`http://YOUR-UNIQNAME.si676.si.umich.edu/`

So, if my uniqname was `umsimumsi`, my server URL would be: `http://umsimumsi.si676.si.umich.edu/`.

To log in you will need a username and password. This depends on your server setup and administration; in the UMSI class, these will be provided during class, in other settings you may need to be in touch with your IT administrator.[^umsi-login]

[^umsi-login]: In 2026, UMSI server logins used the student's uniqname as a username and a variation of the student's UMID number. So, if `umsimumsi`'s UMID was 12345678, their password would be derived from that number.

When you navigate to your server's URL with a browser, you should see something like [](#blank-server-screen).

```{figure} /assets/part03-servers-blank-server-page.jpg
:label: blank-server-screen
:alt: Screenshot of blank LAMP server viewed by web browser
:align: center

Screenshot of blank LAMP server viewed by web browser.
```

# Logging In to Your Server

To interact with your server, you will need to log in!
This book discusses three main ways to interact with your server:

[cPanel](#logging-in-to-cpanel)
: This is a browser-based "control panel" interface.
To access cPanel, navigate to your server's URL and append `:2083`,
which directs the browser to port 2083. There, you will have the option
to log in with the admin username and password for your server.
You can read the [cPanel documentation here](https://docs.cpanel.net/), though it's probably not necessary for our purposes.

[SSH](#ssh-via-the-terminal)
: This is a terminal interface that allows you to interact with your server.
The interface is a bash environment, so you should be able to run shell commands and most regular navigation and file system commands.
Note that this is a restricted environment for security purposes, so it is possible that you may not be able to run all shell commands; and in some cases you may be prompted to enter your username or password to confirm permissions.

[Filezilla](#filezilla-for-file-transfers)
: This is a GUI client that is helpful for moving files to your server.
All of its functions could probably also be accomplished using _SFTP_, which is
a terminal-based protocol. But this file manager is used in some digital collections environments
and provides all of the functions you will need (without learning additional commands). If you prefer graphical over text interfaces, this is for you! 📠

## Logging in to cPanel

Log in to cPanel by navigating to your site's URL, then requesting port `2083`.

1. Open a web browser and use the following template for your URL: `https://YOUR-UNIQNAME.si676.si.umich.edu`
2. At this page, you should see the unconfigured server page (basically, like a listing of files available there.
3. To access the server, you can use the cPanel tools. To do this, access the above url with port 2083. To do this, append a colon (`:`) to the end of the URL and the number `2083`. For example, if your uniqname was `umsimumsi`, you would use the following URL to access cPanel: `https://umsimumsi.si676.si.umich.edu:2083`.
4. The page that opens will prompt you for your login credentials. The login page will look similar to [](#servers-cpanel-login).

```{figure} /assets/part03-servers-cpanel-login-port2083.jpg
:label: servers-cpanel-login
:alt: Screenshot of cPanel login page at port 2083
:align: center

Screenshot of cPanel, logging in via port 2083.
```

When you log in, you should see a screen that looks something like the screenshot below. Notice: at the right, you will see your user information, the name of the domain that connects to your server, the IP address, the path to your home directory (that will be where to add files when we access the server using terminal), and some other information about the setup of cPanel. See [](#servers-cpanel-logged-in).

```{figure} /assets/part03-servers-cpanel-databases.jpg
:label: servers-cpanel-logged-in
:alt: Screenshot of cPanel when logged in
:align: center

Screenshot of cPanel, logged in view.
```

## SSH via the Terminal

To log in with the SSH (Secure SHell), open the client that you use for command shell (e.g., Terminal, GitBash, or other). The command to access your server is `ssh` (secure shell).
To use this command, use the following syntax:

```bash
ssh user@domain.com
```

For `umsimumsi`, the command would look like this:

```bash
ssh umsimumsi@umsimumsi.si676.si.umich.edu
```

In [](#servers-ssh-logging-in), see the command ready to execute in the terminal.

```{figure} /assets/part03-servers-shell-ssh-login.jpg
:label: servers-ssh-logging-in
:alt: Screenshot of a command shell window with the SSH login command ready to run
:align: center

Logging in to `ssh` in the terminal.
```

When you run the command, you will be prompted for your password.
When you type the password, you will not see the response,
which can make it difficult to know if you have typed the right information.
**Type carefully**, then press `Enter` (Windows) or `return` (Mac). If your login is successful, you should see a page notifying you of server policies, which will also ask you to select a dual-factor login method (see [](#servers-ssh-authentication)). Use the method that you are most comfortable with.

```{figure} /assets/part03-servers-ssh-login-dualfactor.jpg
:label: servers-ssh-authentication
:alt: Screenshot of a command shell window requesting dual factor authentication
:align: center

ssh dual factor authentication
```

Note the dual factor option can time out. So if you are not logged in, try again. 

Finally, you'll see a page something like [](#servers-ssh-logged-in), which indicates you have logged in to your server:

```{figure} /assets/part03-servers-ssh-logged-in.jpg
:label: servers-ssh-logged-in
:alt: Screenshot of a command shell window logged in to the server at the root location
:align: center

ssh server logged in
```

From this page, you should be able to navigate and use basic Bash commands.
The most frequent location you will need to access here is the `public_html` directory,
which is where HTTP-accessible files will be located.

**SSH Notes:**

* If you incorrectly enter your password more than three times, the server will be inaccessible for 10 minutes
* You may not be able to log in from off campus unless you are using the U-M VPN since access is restricted by IP range for security purposes

## FileZilla for File Transfers

The final method for accessing your server is the Filezilla client,
which provides a graphical user interface allowing you to use
secure File Transfer Protocol tools.
The Filezilla software is available at Campus Computing sites and is also available
for a 30-day trial version if you wish to download it on your own computer
(see the [Filezilla site for download information](https://filezilla-project.org/download.php)).

The Filezilla login process is unique, but it requires the same information as the previous two methods. Namely, your uniqname, UMID, and server domain address. Here are the basic steps:

First, open the Filezilla client (that is, a software/app you run locally). The window should look similar to [](#servers-filezilla).

```{figure} /assets/part03-servers-filezilla-main-window-macos.jpg
:label: servers-filezilla
:alt: Screenshot of the Filezilla client with main areas highlighted
:align: center

Screenshot of the Filezilla client with main areas highlighted.
```

Take note of the three main parts of the window (see [](#servers-filezilla)).
In the area of rectangle `1.`, you can see the current status of the connection, any file transfers that you execute, and sometimes useful updates as to what Filezilla is doing.
In the area of rectangle `2.`, you have a file browser window that shows files on your local computer (in [](#servers-filezilla), a bar just above the rectangle shows "Local site:", then shows the path as the root of the operating system indicated by the leading slash `/`, then the local directory named `Users`, then the `jajohnst` directory).
The area of rectangle `3.` shows a similar file browser. This file browser, however, shows the files on your server. (At least, it will show those files when you are logged in.) Note the path bar above that rectangle is labelled "Remote site:".

```{figure} /assets/part03-servers-filezilla-site-manager-window.jpg
:label: servers-filezilla-site-manager
:alt: Screenshot of the Site Manager window to log in to your server following dual factor authentication
:align: center

Screenshot of the Site Manager window to log in to your server following dual factor authentication.
```

Second, locate the "Site Manager..." window (as shown in [](#servers-filezilla-site-manager)). This should be found near the top of Filezilla's "File" menu.
Use this window to set up your login. In the box with the "Host:" label, type your server's URL.
Choose "Interactive" in the "Logon Type:" so that you can navigate through the dual-factor authentication process.
Finally, in the box labeled "User:", type your uniqname. When this information is completed, click the "Connect" button.

After you request to connect to the server, you will have the option to select how to comlpete the dual factor process. This window may look a bit misleading as the only option is to enter information in a field with the label "Password:"; despite the fact that you are not entering a password, select the option for dual factor authentication that you want. The rest of the process will follow through on your second device or whatever authentication process you usually follow.

Finally, you are logged in to the server via Filezilla. You can now move files from your local computer to the server, or from the server to your local computer, by clicking and dragging and dropping. similarly to how you would do so in a graphical file browser window (like "Explorer" or "Finder"). Note that you may on some occasions be asked to confirm or renew your login (the password or dual factor process may repeat).

It may take a few moments to get set up, but once you get Filezilla working,
hopefully you will appreciate how this tool assists the file transfer process.

## Resources

- [Related slide deck illustrating the login process][related-slide-deck]
- Using FileZilla Guide TODO

[related-slide-deck]: https://docs.google.com/presentation/d/19wmAE6DZVOh4rOIY9CiLJPbSTWajaWH1mShs8srN4no/edit?usp=sharing
