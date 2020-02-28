---
title: CyberCenturion Scripts
date: 2020-02-28 10:00:00
tags: cybercenturion
---
This year for CyberCenturion, one of our teams decided to make some scripts to automate some of the time consuming, repetitive and more complex tasks in the various rounds. Now that we have completed the competition we have decided to publish our script for others to learn from.

## Overview

We decided to write our script in Python 3.7 so that it would work exactly the same for all of the different operating systems that we would be given. We could have written separate scripts for Windows and Linux instead which would have simplified installation on the different machines, but we wanted to keep everything in one place rather than having to work on different scripts for different operating systems. Writing our scripts in Python also meant that we didn't have to learn about complex Bash and PowerShell/Batch scripting techniques like selection and iteration and we could just use programming knowledge that we already had.

We went for a modular approach to make CentSecure easy to add more features and plugins to. We achieved this by having a main 'loader' that finds 'plugins' in a folder. Each of these plugins achieves one task, for example:

- **Account Management** to create and remove user accounts and make different users admin or a normal user.
- **PAM** to manage the configuration files responsible for logging in on Linux.
- **Firefox** to set Firefox's setting to make it more secure.
- **SSH** for securing SSH.

In the end, we ended up with 20 different 'plugins' that sort out these various tasks.

## Technical Workings

Our main `centsecure.py` file uses functions from `plugin.py` and `common.py` in order to search the `plugins` directory for Python files containing classes of the type `Plugin`. It then takes each of the plugins that it has found and adds them to a master list of plugins.

Depending on which option the script is run with, the list of plugins is looped through and if the OS of the computer matches the OS set on the plugin, the `execute()` function inside the plugin class is run. This is an example of what a plugin file might contain:

```python
import plugin
import common


# This creates a new class of the type 'Plugin' which is what the 'loader' looks
# for.
class LinuxFirewall(plugin.Plugin):
    # This variable sets a human-readable name for the plugin which we didn't
    # end up using, but could have been used in a user interface.
    name = "Enable Linux Firewall"
    # This variable is a list that contains all of the operating systems that
    # the plugin can run on. (e.g. 'Linux' for all Linux distros, 'Ubuntu' for
    # just Ubuntu distros, 'Windows' for all Windows OSes)
    os = ["Linux"]
    # This variable is a list that contains all of the operating system
    # versions that the plugin can run on. (e.g. '16.04' for Ubuntu 16.04)
    os_version = ["ALL"]

    # The execute function in each plugin is run by the main 'loader' file.
    def execute(self):
        # This uses the common file that we created in order to execute the
        # command 'ufw enable' which enables the firewall on Linux machines.
        common.run("ufw enable")
```

We had `common.py` contain lots of functions that we used throughout the plugins for things from logging to downloading files.

### Installation

To simplify installation of CentSecure during the rounds, we decided to create some installer scripts which download Python and anything else that we needed to run CentSecure. These scripts are contained in the `scripts` folder and we had written one for both Windows and Linux.

### Collaboration

Two of us collaborated together on these scripts in order to split up the workload into smaller tasks. We used GitHub so that we could both have access to the code and the changes that each other had made. GitHub also made it easy to publish our source code at the end. We made use of GitHub Issues [here](https://github.com/malvern-cads/centsecure/issues?q=is%3Aissue) to keep track of all of the different features that we needed to add.

To make sure that we used consistent syntax and styling, we used a Python package called `flake8` along with some add-ons to lint our code to make sure that it had consistent styling throughout. We also used [continuous integration](https://en.wikipedia.org/wiki/Continuous_integration) in order to automatically run these style checks for each commit to GitHub.

## Finals

The rules for using scripts in the last round were a bit obscure so we decided to be safe and not use them in the end. We'll talk about how our teams did in the next post, but it was harder to get the points quickly without the script. 

If you're interested in the scripts we have written for CyberCenturion, you can check out the source code and how to use it [here](https://github.com/malvern-cads/centsecure). We also have some documentation for CentSecure [here](https://malvern-cads.github.io/centsecure/) and the following notes that we used for all of the rounds:

- **[Game Plan](https://malvern-cads.github.io/centsecure/game_plan/)** - The plan that we used in the final to work through the different virtual machines.
- **[Common Vulnerabilities](https://malvern-cads.github.io/centsecure/common_vuln/)** - A combined list of all the vulnerabilities from previous rounds.
- **[Previous Vulnerabilities](https://malvern-cads.github.io/centsecure/previous_vuln/)** - A list of the vulnerabilities that we had found from previous rounds. This list is split into years and then the different rounds in that year.
- **[Vulnerability Categories](https://malvern-cads.github.io/centsecure/vuln_categories/)** - A list of the different categorisations that vulnerabilities are put into.