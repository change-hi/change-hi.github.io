---
title: "13. Security"
published: true
morea_id: FairSecurity
morea_type: experience
morea_summary: "What measures will you take to secure your data?"
morea_sort_order: 12
morea_labels:
  - 3:45pm
morea_enable_toc: true
---

# Security

Today, we will approach two different aspects of data security.

- Securing data from hostile people and groups that would compromise the system.
- Securing data from general threats such as power outages, fires, floods, and hardware failure.

Securing data from hostile groups:
Types of attacks

1. _Malware:_ Malicious software. Malware is activated when a user clicks on a malicious link or attachment, which leads to installing dangerous software. Cisco reports that malware, once activated, can:
   -Block access to key network components (ransomware)
   -Install additional harmful software
   -Covertly obtain information by transmitting data from the hard drive (spyware)
   -Disrupt individual parts, making the system inoperable

2. _Emotet:_ The Cybersecurity and Infrastructure Security Agency (CISA) describes Emotet as “an advanced, modular banking Trojan that primarily functions as a downloader or dropper of other banking Trojans. Emotet continues to be among the most costly and destructive malware.”

3. _Denial of Service:_ A denial of service (DoS) is a type of cyber attack that floods a computer or network so it can’t respond to requests. A distributed DoS (DDoS) does the same thing, but the attack originates from a computer network. Cyber attackers often use a flood attack to disrupt the “handshake” process and carry out a DoS. Several other techniques may be used, and some cyber attackers use the time that a network is disabled to launch other attacks. A botnet is a type of DDoS in which millions of systems can be infected with malware and controlled by a hacker, according to Jeff Melnick of Netwrix, an information technology security software company. Botnets, sometimes called zombie systems, target and overwhelm a target’s processing capabilities. Botnets are in different geographic locations and hard to trace.

4. _Man in the Middle:_ A man-in-the-middle (MITM) attack occurs when hackers insert themselves into a two-party transaction. After interrupting the traffic, they can filter and steal data, according to Cisco. MITM attacks often occur when a visitor uses an unsecured public Wi-Fi network. Attackers insert themselves between the visitor and the network, and then use malware to install software and use data maliciously.

5. _Phishing:_ Phishing attacks use fake communication, such as an email, to trick the receiver into opening it and carrying out the instructions inside, such as providing a credit card number. “The goal is to steal sensitive data like credit card and login information or to install malware on the victim’s machine,” Cisco reports.

6. _SQL Injection:_ A Structured Query Language (SQL) injection is a type of cyber attack that results from inserting malicious code into a server that uses SQL. When infected, the server releases information. Submitting the malicious code can be as simple as entering it into a vulnerable website search box.

7. _Password Attacks:_ With the right password, a cyber attacker has access to a wealth of information. Social engineering is a type of password attack that Data Insider defines as “a strategy cyber attackers use that relies heavily on human interaction and often involves tricking people into breaking standard security practices.” Other types of password attacks include accessing a password database or outright guessing.

_An Arms Race_

Cyber security practices continue to evolve as the internet and digitally dependent operations develop and change. Data storage on devices such as laptops and cellphones makes it easier for cyber attackers to find an entry point into a network through a personal device. For example, in the May 2019 book Exploding Data: Reclaiming Our Cyber Security in the Digital Age, former U.S. Secretary of Homeland Security Michael Chertoff warns of a pervasive exposure of individuals’ personal information, which has become increasingly vulnerable to cyber attacks. Increase in both _data use_ and _data sharing_ are contributing to cybersecurity threats. Volume and connectedness both create new areas to exploit.

Strategies to Prevent Hostile Groups from Stealing Data:

- Complex Passwords
- Setting 2 Factor Authentication
- Choosing a Reputible Data Repository

Securing Data from Other Natural Events
Data loss can happen for many reasons such as fires, floods, and hardware failure. The main strategy for preventing this is data redundancy, where data is stored in multiple locations.

Large datasets, will often span multiple hard disks as we approach 1 terabit per square inch (though to be the superparamagnetic limit) of storage density in magnetic hard drives with increasing data size. Storage arrays are ften redundent, redundancy is often created using various types of RAID configurations.

- _Raid 1_ is an exact copy (or mirror) of a set of data on two or more disks.
- _Raid 5_ consists of block-level striping with distributed parity and requires that all drives but one be present to operate. Upon failure of a single drive, subsequent reads can be calculated from the distributed parity such that no data is lost. RAID 5 requires at least three disks.

Small datasets and files are often stored on laptops and computer hard drives. While storage on these devices is more reliable than ever, the data could be lost in the event of damage to the computer. _Data storage is affordable, recreating data is not! Important files should never be in only 1 place._ Cloud storage can be useful for this. Some cloud storage services:

- Dropbox
- GSuite
- OneDrive
- iCloud

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **For more information**
<hr/>
* [Attribution](https://onlinedegrees.und.edu/blog/types-of-cyber-security-threats/) 
* [RAID](https://en.wikipedia.org/wiki/Standard_RAID_levels)
* [BioRDM wiki](https://www.wiki.ed.ac.uk/display/RDMS/).
</div>

{% include next-button.html top-label="Workshop Assessment ->" bottom-label="3:50pm" url="/morea/fair/assessment-fair-workshop.html" %}
