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
Answer: steve/thunder


