# TryHackMe-AuthenticationBypass
<b>Task 2- Username Enumeration</b><br>
So they are asking us to enumerate account credentials of a websites customer signup page utilizing the ffuf tool. We begin by running the command below. <br>
<a href="https://imgur.com/AF6V04C"><img src="https://i.imgur.com/AF6V04C.jpg" title="source: imgur.com" /></a><br>
<br>
Below is the output. We will save the 3 usernames to a text file for later use. <br>
<a href="https://imgur.com/m3CMAwS"><img src="https://i.imgur.com/m3CMAwS.jpg" title="source: imgur.com" /></a>
After running the command, they want us to answer 3 question.
1. What is the username starting with si*** ?<br>
Answer: simon
2. What is the username starting with st*** ?
Answer: steve
3. What is the username starting with ro**** ?
answer: robert
<br>
<b>Task 3- Bruteforce</b><br>
Now they want us to run a password list against the usernames we found to bruteforce in while still using ffuf.<br>
<a href="https://imgur.com/iHaFygF"><img src="https://i.imgur.com/iHaFygF.jpg" title="source: imgur.com" /></a><br>
The output from the command is below and we can see a login/password combo.<br>
<a href="https://imgur.com/rlfXyRs"><img src="https://i.imgur.com/rlfXyRs.jpg" title="source: imgur.com" /></a><br>
<br>
1. What is the valid username and password (format: username/password)?<br>
Answer: steve/thunder<br>
<br>
<b>Task 3- Logic Flaw</b><br>
The next task has us looking to exploit a logic flaw in the account password reset of the websites support page. We will be
using the curl tool to send the request to the server.<br>
<br>
curl 'http://10.10.131.2/customers/reset?email=robert%40acmeitsupport.thm' -H 'Content-Type: application/x-www-form-urlencoded' -d 'username=robert'<br>
<br>
We will then redirect where we want the email sent in the a second curl request. <br>
<a href="https://imgur.com/rrBbUGl"><img src="https://i.imgur.com/rrBbUGl.jpg" title="source: imgur.com" /></a><br>
<br>
And you can see we were able to have the website redirect the email to a malicous account.
<a href="https://imgur.com/kJr1Oxm"><img src="https://i.imgur.com/kJr1Oxm.jpg" title="source: imgur.com" /></a><br>
<br>
Next we will create an account using this email address (@customer.acmeitsupport.thm) on the organizations website and then use the curl tool again to redirect roberts email to our newly created account.
<br>
<a href="https://imgur.com/De5dSR7"><img src="https://i.imgur.com/De5dSR7.jpg" title="source: imgur.com" /></a><br>
<br>
After that we go to check our account on the website to retrieve the support ticket and use the password reset link to access Robert's account.<br>
<a href="https://imgur.com/dlChIjY"><img src="https://i.imgur.com/dlChIjY.jpg" title="source: imgur.com" /></a><br>
<br>
Now we can log in to Robert's account to retieve the flag.
<a href="https://imgur.com/vABQSsP"><img src="https://i.imgur.com/vABQSsP.jpg" title="source: imgur.com" /></a><br>
<br>
What is the flag from Robert's support ticket?<br>
Answer: THM{AUTH_BYPASS_COMPLETE} 




