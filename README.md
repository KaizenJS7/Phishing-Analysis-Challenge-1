<h1>Instructions:</h1>

You are a SOC Analyst at Mighty Solutions, Inc. An account executive, Dana Derringer, noticed a warning email in her inbox claiming her online access has been disabled. However, she noticed this was odd as she is still able to access her online business platforms and inbox. She decided to forward the email in question to the security team's phishing mailbox for review.

Using what you've learned within this domain, perform a detailed email analysis on the <b>challenge1.eml</b> file to answer the report questions below.

<b>Challenge File:</b>

    01_Phishing_Analysis/Challenges/challenge1.eml

<h2>Question 1</h2>

<b>Based on the contents of the email header, what is the full date and time of the email delivery?</b>

For the first question let's start by opening the email that Dana sent us in Thunderbird.

<img src="https://i.imgur.com/8b1BVLM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

If you notice on the top right highlighted in orange we have our date and time! but this isn't what the question is asking us and sadly this isn't the answer to our question, so let's do a bit more digging by opeing up the email in <b>Sublime Text</b> as follows.

    subl challenge1.eml

   <img src="https://i.imgur.com/cVqc35W.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

 <img src="https://i.imgur.com/5CPmXPd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />


If we scroll down to where it says <b>Date:</b> we will find our answer there!

 <img src="https://i.imgur.com/gd7hzkB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

- <b>Answer:</b>

      Tue, 31 Oct 2023 10:10:04 -0900

  <h2>Question 2</h2>

<b>What is the subject of the email?</b>

Just like the first question, let's find where it says <b>Subject:</b> and our answer should be there.
  
 <img src="https://i.imgur.com/7nX54wU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

- <b>Answer:</b>

      Your account has been flagged for unusual activity

<h2>Question 3</h2>

<b>Who was the email sent to?</b>

Like the previous questions, let's find <b>To:</b> to answer question 3!

<img src="https://i.imgur.com/yZbTGRA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

- <b>Answer:</b>

      dderringer@mighty-solutions.net

<h2>Question 4</h2>

<b>Based on the sender's display name, who does the email claim to be from?</b>

Same as previous questions, let's look for <b>From:</b>

<img src="https://i.imgur.com/i9imOd3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

- <b>Answer:</b>

      Outlook Support Team

<h2>Question 5</h2>

<b>What is the sender's email address?</b>

The answer is in the same line as <b>From:</b> of the previous question.

<img src="https://i.imgur.com/w0xOxVr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

- <b>Answer:</b>

      social201511138@social.helwan.edu.eg

<h2>Question 6</h2>

<b>What email address is used for receiving bounced emails?</b>

To search for bounced emails we have to look for <b>Return-Path:</b>.

<img src="https://i.imgur.com/vl5Wa0I.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

- <b>Answer:</b>

      social201511138@social.helwan.edu.eg

<h2>Question 7</h2>

<b>What is the IP address of the sender's email server?</b>

To know the IP address of the sender's email server, we have to navigate to <b>X-Sender-IP:</b>

<img src="https://i.imgur.com/bSWCWeC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

- <b>Answer:</b>

      40.107.22.60

<h2>Question 8</h2>

<b>What is the resolved hostname of the sender's IP address?</b>

To answer this question will go to our prefered browser and utilize a tool called  <b>Whois Lookup (https://whois.domaintools.com)</b>. After we reach our tool site, let's paste the IP address we found previously and click search.

<img src="https://i.imgur.com/tJdA2Md.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

After the page loads, we can find our answer under <b>Resolve Host</b>

<img src="https://i.imgur.com/kaAai4c.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

- <b>Answer:</b>

      mail-am6eur05on2060.outbound.protection.outlook.com

<h2>Question 9</h2>

<b>What corporation owns the sender's IP address?</b>

In the same page under <b>ASN</b>, well find our answer to question 9.

<img src="https://i.imgur.com/SylIjin.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

- <b>Answer:</b>

      MICROSOFT

<h2>Question 10</h2>

<b>What was the result of the SPF check?</b>

To answer this question we have to go back to <b>Sublime Text</b>, and then we will look for <b>Received-SPF:</b>.

<img src="https://i.imgur.com/mA742S7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

- <b>Answer:</b>

      Pass

<h2>Question 11</h2>

<b>What is the full SPF record of the sender's domain?</b>

To answer this question we will need to open up our terminal and paste the following command.

      nslookup -type=txt social.helwan.edu.eg | grep -i spf

The "<b>nslookup -type=txt</b>" command is used to query the DNS (Domain Name System) for TXT (text) records associated with a specific domain name. 

The "<b>social.helwan.edu.eg</b>" is the sender's domain we found under the <b>From:</b> header.

And the "<b>| grep -i spf</b>" command is used to search for lines containing the term "spf" in a case-insensitive manner. This is often used when examining DNS records or email headers to find information related to SPF (Sender Policy Framework) records.

<img src="https://i.imgur.com/yVmzf6r.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<img src="https://i.imgur.com/ZizYX0m.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

- <b>Answer"</b>

      v=spf1 include:spf.protection.outlook.com -all

<h2>Question 12</h2>

<b>What is email's Message ID?</b>

Navigate to <b>Sublime Text</b> and look for the header <b>Message-ID:</b>

<img src="https://i.imgur.com/jX3aQje.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

- <b>Answer:</b>

      JMrByPl2c3HBo8SctKnJ5C5Gp64sPSSWk76p4sjQ@s6

<h2>Question 13</h2>

<b>What type of encoding was used to transfer the email body content?</b>

This will be under the header <b>Content-Transfer-Encoding:</b>

<img src="https://i.imgur.com/zIAZ8BJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

- <b>Answer:</b>

      base64

<h2>Question 14</h2>

<b>In defanged format, what is the second URL extracted from the email?</b>

For us to be able to defange this format, we will use a tool called <b>Cypher Chef (https://gchq.github.io/CyberChef/)</b>, but first let's copy the Base64 content of our email.

<img src="https://i.imgur.com/1G0262u.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

Then will navigate to <b>Cypher Chef</b> and paste our Base64 content in the top right window under <b>Input</b>.

<img src="https://i.imgur.com/QjNbJyE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

Next will go over under the <b>Operations</b> window and search for "<b>From Base64</b>","<b>Extract URLs</b>", "<b>Defang URL</b>", and drag every single one onto the <b>Recipe</b> window. If done correctly, we will find our second defanged URL in the bottom right window under <b>Output</b>.

<img src="https://i.imgur.com/I1rAHx7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

- <b>Answer:</b>

      hxxps[://]0[.]232[.]205[.]92[.]host[.]secureserver[.]net/lclbluewin08812/

<h2>Question 15</h2>

<b>Perform a VirusTotal scan on the URL. What verdict did Fortinet assign to it?</b>

As the questions says, let's navigate to <b>Virus Total (https://www.virustotal.com)</b> and paste the URL under the URL scan (Don't forget to unDefang the URL in Cypher Chef before you paste it into Virus Total) and then hit enter.

<img src="https://i.imgur.com/jr5n7DG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

After look for the section <b>Security vendor's analysis</b> and search for <b>Fortinet</b> and our answer is there.

<img src="https://i.imgur.com/4pZlDcD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

- <b>Answer:</b>

       Phishing

<h2>Question 16</h2>

<b>[Yes or No] - After your analysis, is this email genuine?</b>

- <b>Answer:</b>

      No

<h2></h2>

<b>Thank you TCM Security for this hands on Phishing Lab Challenge!</b>

For more information visit their website at https://academy.tcm-sec.com/
