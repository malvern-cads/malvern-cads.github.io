---
date: 2020-01-13 16:30:21
categories:
- sessions
tags:
- security
title: The Cyber Kill Chain

---
This week was a bit quiet because of mock exams going on for the year 13s. As there weren't many of us we were going to continue working on the board for advertising CADS at out school.

Unfortunately, because of people being away, we couldn't get any of the stuff that we needed to continue working on the board so we had an impromptu presentation on the cyber kill chain.

The cyber kill chain consists of 7 different phases which describe the way that most cyber attacks happen. This kill chain is mainly used for helping to secure a network against attacks by locking down how each of the phases can happen. Here are each of the phases:

1. **Reconnaissance**: This stage includes selecting a target, researching about it and attempting to find vulnerabilities that can be used to gain access into the network.
2. **Weaponization**: The attackers will then create some malware (which is a malicious program) that can use the vulnerabilities found in the previous step in order to gain access to the network.
3. **Delivery**: The weapon is then delivered to the target usually through an e-mail attachment, malicious website or an infected USB drive.
4. **Exploitation**: Now that the weapon has been delivered, it is triggered on the target (by clicking on the e-mail's attachment, opening the website or plugging in the USB drive) which runs the malware and uses the vulnerability from the reconnaissance step to gain access to the network.
5. **Installation**: The weapon installs an access point (usually a backdoor) which is then able to be accessed by the attacker remotely.
6. **Command and Control**: A server communicates with the weapon and allows the attacker to remotely execute commands.
7. **Actions on Objective**: The attacker takes action to achieve their goals (such as stealing some data or destroying data).

![](/uploads/cyber kill chain.jpg)

This is pretty difficult to get your head around without an example, so we were told about a virus called [Stuxnet](https://en.wikipedia.org/wiki/Stuxnet) which was used to take down the Iranian nuclear program.

So for reconnaissance, the attackers watched a video someone uploaded to YouTube which was a tour of the facility. In the background they managed to see a computer monitor and identify what operating system it was running. They noticed that the operating system that they were using was old and so had some vulnerabilities that they could exploit. They probably did some more research, but this is one of the most important pieces of information that they found out.

Next up, they made their 'weapon' using the vulnerability that they found in the reconnaissance step. They decided to use a [worm](https://en.wikipedia.org/wiki/Computer_worm) virus so that it could infect any computer and then spread across the network to the computer that they were targeting.

In the delivery stage, they loaded the virus onto multiple USB drives and left them scattered around the nuclear facility car park and waited for people to pick them up out of curiosity.

At least one of the employees plugged one of these USB drives into a computer and then the vulnerability in the old operating system was exploited in order to gain access to the network.

For the installation and action on objective stages, the virus changed some software to make the centrifuges of the power plant spin faster than they should. This wasn't able to be detected by the employees and eventually they span so fast that they destroyed themselves. This was detrimental for the Iranians and it set back their nuclear program by many years.

This is just a simplified version of the story to show how each of the phases of the cyber kill chain are applied to a real-life attack, but it's a very interesting story and it's worth reading up about. _If you're interested in learning more_ [_this podcast episode_](https://pca.st/b9d0) _is very interesting!_