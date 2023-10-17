---
title: "Install RClone"
published: true
morea_id: reading-rclone
morea_type: reading
morea_summary: "Installing RClone on your local machine"
morea_sort_order: 2
morea_labels:
    - Pre-workshop
morea_enable_toc: true
---

## Preparation: Install RClone on your Machine

Rclone installation can be found [here](https://rclone.org/install/). The documentation includes instructions for Windows, MacOS, Linux, etc.


### Windows

1) Download the relevant binary from [RClone](https://rclone.org/downloads/)

2) Create a new `rclone` file in your `C:\`

3) Extract the downloaded files to `C:\rclone`

4) Navigate to 'Settings' > 'Advanced System Settings' > 'Environment Variables'

5) Select 'Path' and click 'Edit'

6) Click 'New' and 'Browse', for Browse for folder, and navigate to `C:\rclone`, click 'OK' for all menus

RClone should now be installed on your machine. Navigate to your Powershell to confirm that the rclone command is functioning.

Test with:
`rclone config`




* We recommend [Chrome](https://www.google.com/chrome/) or [Firefox](https://www.mozilla.org/en-US/firefox/).  Internet Explorer is not recommended.