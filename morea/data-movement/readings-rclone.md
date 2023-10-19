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

Rclone installation documentation can be found [here](https://rclone.org/install/). The documentation includes instructions for Windows, MacOS, Linux, etc.


### Windows 10 Installation


#### Download and Install
1) Download the relevant file from [RClone](https://rclone.org/downloads/)
 {% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone_Install_1.png" alt="Node anatomy" caption="" %}

2) On your machine, create a new `rclone` folder in your `C:\`

3) Extract the downloaded files to `C:\rclone`
 {% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone_Install_2.png" alt="Node anatomy" caption="" %}

#### Add RClone to Path
4) Navigate to 'Advanced System Settings' > 'Environment Variables'
 {% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone_Install_3.png" alt="Node anatomy" caption="" %}


5) In 'User Variables', select 'Path' and click 'Edit'
 {% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone_Install_4.png" alt="Node anatomy" caption="" %}


6) In the 'Edit environment variable window, click 'New' and 'Browse', for Browse for folder, and navigate to `C:\rclone`, click 'OK' for all menus
 {% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone_Install_5.png" alt="Node anatomy" caption="" %}

#### Test
RClone should now be installed on your machine. Navigate to your CLI to confirm that the `rclone` command is functioning.

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ rclone version
```
</div>

The output of the command should show information for RClone and your system.

Powershell Example:

 {% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone_Install_6.png" alt="Node anatomy" caption="" %}




* We recommend [Chrome](https://www.google.com/chrome/) or [Firefox](https://www.mozilla.org/en-US/firefox/).  Internet Explorer is not recommended.


{% include next-button.html
  top-label="RClone Config. ->"
  bottom-label=""
  url="/morea/data-movement/experience-configuring-rclone.html" %}
