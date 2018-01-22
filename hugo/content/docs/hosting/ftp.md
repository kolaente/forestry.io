---
title: FTP/SFTP
weight: 5
publishdate: 2017-12-31 04:00:00 +0000
expirydate: 2030-01-01 04:00:00 +0000
date: 2017-12-31 00:00:00 -0400
menu:
  docs:
    parent: hosting
layout: single
---
{{% tip "Disclaimer" %}}
This guide assumes you already have an existing [Forestry Account](https://app.forestry.io/signup), a webserver with FTP access, and a repository with a Jekyll or Hugo project. If you don't have an existing project, check out our [Quick start guide](/docs/welcome/quick-start), which contains guides and resouces for building your first static site.
{{% /tip %}}

## Overview
In order for Forestry to deploy your site via FTP/SFTP, you will need:

* A webserver with FTP/SFTP support
* A valid FTP username and password
* The port your FTP server uses

If you are hosting your static site on an FTP server, you should be aware that Forestry will delete all files from your destination directory before  writing the new, updated files.

This could be problematic if you keep non-website related files in your FTP account. If you don't want Forestry to empty all of your files, consider setting up your site in an empty subdirectory.

## Choosing an FTP Method
Forestry provides four FTP connection methods:

### FTP
Basic, unsecured FTP. Usually served via port 21.

### FTP with TLS/SSL (FTPES)
FTP secured via TLS/SSL encryption. Usually served via port 990. Also known as FTP with explicit SSL.

FTP with TSL/SSL will fallback to basic FTP if a secured connection cannot be established.

### FTP with Implicit SSL (FTPS)
FTP secured via TLS/SSL encryption. Usually served via port 990. Also known as FTP with explicit SSL.

FTP with Implicit SSL will not connect if a secured connection cannot be established.

### SFTP (SSH FTP)
FTP secured with SSH. Usually served over port 22.

SFTP can optionally authenticate using an SSH keypair instead of a username & password combination.

{{% tip %}}
Whenever possible, use SFTP or FTP with Implicit SSL to ensure the best security for your webserver.
{{% /tip %}}

## Configuring Forestry
Once you have your FTP credentials and have chosen the correct FTP method for your webserver, navigate to the *Settings* page of your site in Forestry, click the *Hosting* tab, and set the *Connection* option to your desired FTP connection type.

### FTP, FTPS, & FTPES
TK: image

Next, enter your webservers host, username, and password.

Under *Advanced Options*, ensure that the *Port* is the correct port.

If you created a new directory to deploy your site to, provide the relative path from your FTP users home folder to the new directory in the *Directory* field.

Finally, click *Save Settings*.

From here on, every time you save or publish a page Forestry will build your site and deploy to your webserver.

{{% warning %}}
When saving your hosting settings, Forestry will attempt to connect to your FTP server. If a connection cannot be established, an error will be displayed.
{{% /warning %}}

### SFTP
TK: image

Next, enter your webservers host, username, and password. If you're using an SSH keypair to authenticate, upload your public key using the *SSH Key* field.

Under *Advanced Options*, ensure that the *Port* is the correct port.

If you created a new directory to deploy your site to, provide the relative path from your FTP users home folder to the new directory in the *Directory* field.

From here on, every time you save or publish a page Forestry will build your site and deploy to your webserver.

{{% warning %}}
When saving your hosting settings, Forestry will attempt to connect to your SFTP server. If a connection cannot be established, an error will be displayed.
{{% /warning %}}