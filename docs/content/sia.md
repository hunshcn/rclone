---
title: "Sia"
description: "Rclone docs for Sia"
date: "2019-10-02"
---

<i class="fa fa-globe"></i> Sia
-----------------------------------------

Sia is the [Sia Decentralized Cloud](https://sia.tech/).

You will need to be running a copy of Sia-UI or siad, locally or on your LAN (e.g. a NAS).  Sia's HTTP API is required and typically listens on port 9980.

Here is an example of how to make a remote called `remote`.  First run:

     rclone config

This will guide you through an interactive setup process:

```
No remotes found - make a new one
n) New remote
s) Set configuration password
q) Quit config
n/s/q> n
name> remote
Type of storage to configure.
Enter a string value. Press Enter for the default ("").
Choose a number from below, or type in your own value
...
29 / Sia Decentralized Cloud
   \ "sia"
30 / Transparently chunk/split large files
   \ "chunker"
31 / Union merges the contents of several remotes
   \ "union"
...
Storage> 29
** See help for sia backend at: https://rclone.org/sia/ **

Sia HTTP API URL
Like http://127.0.0.1:9980
Enter a string value. Press Enter for the default ("").
api_url> http://127.0.0.1:9980
Sia API Password
siad API Password
y) Yes type in my own password
g) Generate random password
n) No leave this optional password blank
y/g/n> y
Enter the password:
password:
Confirm the password:
password:
Edit advanced config? (y/n)
y) Yes
n) No
y/n> n
Remote config
--------------------
[remote]
type = sia
api_url = http://127.0.0.1:9980
api_password = *** ENCRYPTED ***
--------------------
y) Yes this is OK
e) Edit this remote
d) Delete this remote
y/e/d> y
Current remotes:

Name                 Type
====                 ====
remote               sia

e) Edit existing remote
n) New remote
d) Delete remote
r) Rename remote
c) Copy remote
s) Set configuration password
q) Quit config
e/n/d/r/c/s/q> q
```

Once configured you can then use `rclone` like this,

List directories in top level of your Sia storage

    rclone lsd remote:

List all the files in your Sia storage

    rclone ls remote:

To copy a local directory to an Sia directory called backup

    rclone copy /home/source remote:backup


<!--- autogenerated options start - DO NOT EDIT, instead edit fs.RegInfo in backend/sia/sia.go then run make backenddocs -->
### Standard Options

Here are the standard options specific to sia (Sia Decentralized Cloud).

#### --sia-api-url

Sia HTTP API URL
Like http://127.0.0.1:9980

- Config:      api_url
- Env Var:     RCLONE_SIA_API_URL
- Type:        string
- Default:     ""

#### --sia-api-password

Sia API Password
siad API Password

- Config:      api_password
- Env Var:     RCLONE_SIA_API_PASSWORD
- Type:        string
- Default:     ""

### Advanced Options

Here are the advanced options specific to sia (Sia Decentralized Cloud).

#### --sia-sia-user-agent

Siad User Agent
Sia requires a 'Sia-Agent' user agent by default for security

- Config:      sia_user_agent
- Env Var:     RCLONE_SIA_SIA_USER_AGENT
- Type:        string
- Default:     "Sia-Agent"

<!--- autogenerated options stop -->