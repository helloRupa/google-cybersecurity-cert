# Cybersecurity Incident Report: Brute force attack

You are a cybersecurity analyst for yummyrecipesforme.com, a website that sells recipes and cookbooks. A former employee has decided to lure users to a fake website with malware.

The former employee/ hacker executed a brute force attack to gain access to the web host. They repeatedly entered several known default passwords for the administrative account until they correctly guessed the right one. After they obtained the login credentials, they were able to access the admin panel and change the website’s source code. They embedded a javascript function in the source code that prompted visitors to download and run a file upon visiting the website. After embedding the malware, the hacker changed the password to the administrative account. When customers download the file, they are redirected to a fake version of the website that contains the malware.

Several hours after the attack, multiple customers emailed yummyrecipesforme’s helpdesk. They complained that the company’s website had prompted them to download a file to access free recipes. The customers claimed that, after running the file, the address of the website changed and their personal computers began running more slowly.

In response to this incident, the website owner tries to log in to the admin panel but is unable to, so they reach out to the website hosting provider. You and other cybersecurity analysts are tasked with investigating this security event.

To address the incident, you create a sandbox environment to observe the suspicious website behavior. You run the network protocol analyzer tcpdump, then type in the URL for the website, yummyrecipesforme.com. As soon as the website loads, you are prompted to download an executable file to update your browser. You accept the download and allow the file to run. You then observe that your browser redirects you to a different URL, greatrecipesforme.com, which contains the malware.

The logs show the following process:

    The browser initiates a DNS request: It requests the IP address of the yummyrecipesforme.com URL from the DNS server.

    The DNS replies with the correct IP address.

    The browser initiates an HTTP request: It requests the yummyrecipesforme.com webpage using the IP address sent by the DNS server.

    The browser initiates the download of the malware.

    The browser initiates a DNS request for greatrecipesforme.com.

    The DNS server responds with the IP address for greatrecipesforme.com.

    The browser initiates an HTTP request to the IP address for greatrecipesforme.com.

A senior analyst confirms that the website was compromised. The analyst checks the source code for the website. They notice that javascript code had been added to prompt website visitors to download an executable file. Analysis of the downloaded file found a script that redirects the visitors’ browsers from yummyrecipesforme.com to greatrecipesforme.com.

The cybersecurity team reports that the web server was impacted by a brute force attack. The disgruntled hacker was able to guess the password easily because the admin password was still set to the default password. Additionally, there were no controls in place to prevent a brute force attack.

## Section 1: Identify the network protocol involved in the incident

The HTTP protocol is involved. yummyrecipesforme.com is served over HTTP, as is greatrecipesforme.com. The malicious file is also served over HTTP at the application layer.

## Section 2: Document the incident

A threat actor used a brute force attack to gain access to the administration panel of the website. They then changed the credentials to maintain access and lock others out. While in the system, they updated the website's source code by replacing it with a download for a malicious file. Users were tricked into downloading the file with the promise of free recipes. Upon downloading the file, users were redirected to a malicious site greatrecipesforme.com, which contained malware. Their computers also began to run slower.

The attack was reported by customers several hours after the incident began. The website owner attempted to log in to the admin panel, but was unable to do so and reported the incident to the cybersecurity team.

The analyst accessed the website in a sandbox environment, and then ran a tcpdump. The analyst observed that the website was requesting they download a file to get free recipes. They downloaded the file and ran it, resulting in being redirected to the malicious site.

An analyst also reviewed the website's source code and discovered it had been manipulated to prompt for the malicious download. Since the website owner was locked out of the admin panel, the analyst also believes that a brute force attack was used to gain access and change the credentials.

## Section 3: Recommend one remediation for brute force attacks

The company should disallow previous passwords from being used, since a default password was ultimately used to obtain access to the admin panel. All default passwords should be disallowed as passwords.

The company should configure company-wide password policies, including strong passwords not found in a rainbow table, a maximum number of retries, and password upadates every 3 to 6 months. MFA or 2FA can also be configured.
