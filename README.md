# Cryptography-Application-Security
Here is the summary of Cybersecurity Web Vulnerability Analysis (Lab 1 &amp; Lab 2)

This project focuses on identifying hidden vulnerabilities within HTML files in two separate lab environments. The tasks simulate real-world Capture The Flag (CTF) challenges and web-based security assessments where the objective is to analyze source code, detect hidden clues, and uncover flags. The project is divided into Lab 1 and Lab 2, each using extracted folders containing multiple HTML documents arranged across different levels.

📁 Lab 1 — HTML Source Code Vulnerability Discovery.

In Lab 1, the extracted project folder contains two directories: “Topic 2 Lab 2” and “ctf.” The initial task is performed inside the Topic 2 Lab 2 directory. The objective is to manually inspect HTML files to locate hidden vulnerabilities or embedded flags.

Only Chrome HTML Documents are examined. Each file is opened and its source code viewed using the shortcut Ctrl + U or by right-clicking and selecting “View Page Source.” This allows visibility into embedded comments, hidden directories, or suspicious code segments not visible on the user interface.

By systematically checking all the files, one specific HTML file was identified as containing a hidden element. The file was located deep inside multiple nested folders under the path:

    Topic 2 Lab 2\LAB\secret\hidden\superhidden\index


This file contained a hidden flag inside the HTML structure, revealing an embedded vulnerability. The discovery illustrates how sensitive information can be unintentionally exposed in deeply nested directories, emphasizing the importance of secure coding practices and regular code audits.

📁 Lab 2 — Multi-Level CTF Web Vulnerability Challenge.

Lab 2 focuses entirely on the “ctf” folder. Inside this directory, a main HTML file contains multiple hyperlinks leading to Levels 1 through 5. Each level represents a unique vulnerability assessment challenge.

🔸 Level 1

Opening the Level 1 hyperlink and viewing its source code reveals a vulnerability hidden inside an HTML comment. This demonstrates a common beginner-level flaw where sensitive hints or data are left in comments.

🔸 Level 2

Similar to Level 1, Level 2 also contains vulnerabilities embedded as commented lines. These comments provide clues or flags that would not be seen by a regular website user.

🔸 Level 3

Upon inspection, the Level 3 source code contains no vulnerabilities. This level acts as a control example demonstrating proper security hygiene and minimal surface exposure.

🔸 Level 4

Level 4 redirects to a new webpage displaying the message: “Ask robot for help.” This hints at the presence of a robots.txt file within the CTF folder. By navigating through the folder and opening robot.txt, an additional vulnerability is discovered. This reflects a common oversight where sensitive directories are revealed through misconfigured robots.txt files.

🔸 Level 5

Level 5 contains a reference to Base64 encoding in its source code. A Base64-encoded string is found in the comments. Using Kali Linux, the string is decoded via:

    echo <encoded_string> | base64 --decode


Decoding reveals the Level 5 vulnerability along with the hidden flag.

✅ Conclusion

Both labs emphasize essential cybersecurity techniques, including source-code analysis, directory inspection, comment auditing, Base64 decoding, and identification of hidden files. These exercises reinforce fundamental skills used in penetration testing and CTF competitions, highlighting the importance of examining behind-the-scenes code and configurations to uncover security weaknesses.
