# Ancora-Education-Ucertify-Lab54
# Securing User Accounts

> **Original Lab Source**
> 
> This lab was available through:
>
> [https://ancoraeducation.ucertify.com/app/?func=navigate_items&item_sequence=7]

## Objective of the Lab
In this lab, you will learn to secure user accounts. User account security policies help ensure that user accounts are protected and properly secured. 
## Instructions 
### STEP 1 
From the left sidebar, open the Terminal icon. 
### STEP 2 
Execute the following commands to create a user account named sue:
```bash
useradd -d /home/sue -m -f 60 -e 2025-01-01 -G games -K PASS_MAX_DAYS=60 -K PASS_MIN_DAYS=2 -K PASS_WARN_AGE=10 sue
```
### STEP 3
Execute the following commands to create a password:
```bash
passwd sue
```
### CAUTION
* Provide the new password as ucertify
* Re-enter the password as ucertify
* You will not be able to see the password being typed in.
### STEP 4
Execute the following commands to modify your password:
```bash
vim /etc/pam.d/common-password
```
### STEP 5
Press i and add the following at line 12 before The "obscure" option line in the common-password file to change the minlen= value on the pam_cracklib:
```bash
password requisite pam_cracklib.so retry=3 minlen=12 difok=3
```
### STEP 6
Remove #, press the Esc key, then type (:wq) and press Enter to save the file.
## Disclaimer

This repository is for **educational and personal learning purposes only**.  

The original lab content belongs to **uCertify / Ancora Education** and remains their copyrighted material.  
This repository is not affiliated with, endorsed by, or sponsored by uCertify or Ancora Education.  

No copyright infringement is intended.  
Use of any tools or techniques mentioned here should only be performed in authorized, legal environments.
