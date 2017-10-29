# CybersecurityWeek8Assignment
Facebook Codepath

# Project 8 - Pentesting Live Targets

Time spent: 3 hours spent in total

> Objective: The challenge is to attempt to find and exploit the vulnerabilities. The goal is to identify which two vulnerabilities of each site: red, green, and blue.

The following **required** functionality is completed:

1. [X]  Required: Challenge 1 - Username Enumeration
1. [X]  Required: Challenge 2 - Insecure Direct Object Reference (IDOR)
1. [X]  Required: Challenge 3 - SQL Injection (SQLi)
1. [X]  Required: Challenge 4 - Cross-Site Scripting (XSS)
1. [X]  Required: Challenge 5 - Cross-Site Request Forgery (CSRF)
1. [X]  Required: Challenge 6 - Session Hijacking/Fixation


## Challenge 1: Username Enumeration
- Vulnerability Site: Green
- Vulberability: If you enter in the name of a known user like pperson and a random password,  you will recieve an error message.  The error message is bold, but if you enter in a random username like allie and a password it is not bold.  The programmer indicates found users by making their unsuccessful logins bold, which can be exploited.

Here's a walkthrough of implemented vulnerability:

![week8 1](https://user-images.githubusercontent.com/10890766/32146536-71b63dfe-bcaf-11e7-93f7-c8063c7c7cd8.gif)

GIF created with [LiceCap](http://www.cockos.com/licecap/).


## Challenge 2: Insecure Direct Object Reference (IDOR)
- Vulnerability Site: Red
- Vulberability: You have a screen of salepeorsons and their territories on each site.  
The Sales Peorson Names and ID:
  - ID: 1 NAME: Daron Burke
  - ID: 2 NAME: Sherry Trevino
  - ID: 3 NAME: Irene Boliing
  - ID: 4 NAME: Robert Hamilton
  - ID: 5 NAME: Ken Barker
  - ID: 6 NAME: Elizabeth Olson
  - ID: 7 NAME: Samuel Hunter
  - ID: 8 NAME: Kim Stanley
  - ID: 9 NAME: Barbara Hinckley

On the red site if you enter in the numbers 10 and 11 in the url, you are able to see Testy McTesterson and Lazy Lazyman who are not visible on the Green and Blue sites.  The programmer did not disable those users on the red site leaving the IDOR vulnerability.

Here's a walkthrough of implemented vulnerability:

![week8 2](https://user-images.githubusercontent.com/10890766/32146537-73377a44-bcaf-11e7-955d-b2937b2cc7af.gif)

GIF created with [LiceCap](http://www.cockos.com/licecap/).


## Challenge 3: SQL Injection (SQLi)
- Vulnerability Site: Blue
- Vulberability: Sanatizing your data is very important when using SQL databases, but the salesperson information for the blue site does not sanatize the data for the name and feedback fields.  Attackers can exploit this and in our case we will use the command %27%20OR%20SLEEP(5)=0--%27 when setting the ID.
    This causes the page to take 5 seconds to change and defaults back to the first user David Burke.

Here's a walkthrough of implemented vulnerability:

![week8 3](https://user-images.githubusercontent.com/10890766/32146538-77d04946-bcaf-11e7-9f7b-611107f16b27.gif)

GIF created with [LiceCap](http://www.cockos.com/licecap/).


## Challenge 4: Cross-Site Scripting (XSS)
- Vulnerability Site: Green
- Vulberability: The problem with the green site is that if you create an alert message and insert it into the the comments section you will see the alert message every time you click on the contact messages in your nonpublic screen.
The alert message: <script>alert('found the xss exploit');</script>

Here's a walkthrough of implemented vulnerability:

![week8 4 xss](https://user-images.githubusercontent.com/10890766/32146541-7c074b68-bcaf-11e7-9b28-d98180054dfc.gif)

GIF created with [LiceCap](http://www.cockos.com/licecap/).


## Challenge 5: Cross-Site Request Forgery (CSRF)
- Vulnerability Site: Red
- Vulberability: You can spoof a POST request that utilizes the user's session ID to forge a request to the database.  When you execute that POST request you can edit salesperson information. When you return to the sales list you will see the changed salesperson.

Here's a walkthrough of implemented vulnerability:

![week8 5](https://user-images.githubusercontent.com/10890766/32146544-7f277f52-bcaf-11e7-9e83-d4c9d7eb5b41.gif)

GIF created with [LiceCap](http://www.cockos.com/licecap/).

## Challenge 6: Session Hijacking/Fixation
- Vulnerability Site: Red
- Vulberability: The SessionID is not secure and the contents of the packet are forwarded to additional sites.  I was able to login in to the red site and also be logged in to the blue site without actually logging into the blue site.
Here's a walkthrough of implemented vulnerability:

![week8 6](https://user-images.githubusercontent.com/10890766/32146546-80d7cc44-bcaf-11e7-88d8-d4440af42526.gif)

GIF created with [LiceCap](http://www.cockos.com/licecap/).

## Notes
This lab was fun.

## License

Copyright [2017] [Allie Howe]

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.






