# linux-permission-investigation
Linux Security Investigation: Malicious User Detection
Overview


This project documents a security investigation on an Ubuntu Server system to identify a malicious user exploiting misconfigured file permissions.

Environment
Ubuntu Server (VirtualBox)

Command-line investigation

Multi-user system

Key Findings
Users had access to shared directories with improper permissions

Sensitive data was stored in ZIP files across multiple user directories

Vanessa’s note indicated suspicion toward Alejandro

Chema’s directory was properly restricted, highlighting inconsistent security controls

Malicious User


Alejandro

Root Cause


Misconfigured permissions allowed excessive access (e.g., rwxrwxrwx) and lacked proper use of the sticky bit, enabling users to access or modify files they did not own.

Impact
Unauthorized file access

Potential data manipulation

Weak user isolation

REMEDIATION 
chmod 750 /directory
chmod 1770 /shared_directory
sudo deluser username sudo

Use stronger encryption (e.g., PGP) instead of ZIP files for sensitive data

Skills Demonstrated:

Linux command-line investigation

File permission analysis

Security reasoning

