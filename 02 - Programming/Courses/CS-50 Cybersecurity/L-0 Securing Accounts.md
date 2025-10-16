## Security

```ad-Definition
title: Authorization
Authorization is the act of verifing that you are, indeed, the person who should have access to this account
```

```ad-Definition
title: Usernames and Passwords
Usernames and Passwords are the ways that you attest that you should have access to an account.
```

## Types of Attack

##### 1. Dictionary Attack
Here the attacker attempts to guess your password.
##### 2. Brute-Force Attack
Hackers try lengthy lists of possible passwords to attempt to guess your password.

For example, if your password was secured by four-digit password i.e 10000 possible digits which would take only milliseconds.
If we asked for a password that was four letters, numbers, or punctuation? We would have over 78,000,000 possibilities open to us!

##### 3. Key logging
Usernames, passwords, and OTPs are vulnerable to adversaries logging your keystrokes. Key logging is accomplished by installing malicious software on a computer.

##### 4. Credential Stuffing
It involves the use of an obtained list of usernames and passwords from a compromised website on another website.
Solution: If you are using the same password on multiple websites, best to change them to unique passwords.

##### 5. Social Engineering
Rather than a technological attack, a social engineering attack involves the use of social pressure and trust to compromise your credentials.
Solution: Never tell your password to anyone.

##### 6. Phishing
Phishing uses social engineering in a technological way to obtain your credentials and details by posing as a trusted website.
Solution: Never blindly trust links provided in emails. Consider going to a web browser and directly typing a trusted URL there.

##### 7. Machine-in-the-Middle Attacks
Devices in between you and the source of the data you are downloading, such as routers and switches, can be compromised by very sophisticated attackers.


### National Institute of Standards and Technology (NIST)
NIST issues recommendations on how to protect your accounts more effectively. Some of their recommendations includes
1. Memorized secrets should be at least eight characters in length.
2. Verifiers should allow all printed ASCII characters and Unicode symbols up to 64 characters in length.
3. Verifiers should compare prospective secrets against available dictionary words, repeat sequences, breached password lists, and context-specific words.
4. Verifiers should not allow unauthenticated claimants to access password hints.
5. Verifiers should not require periodic changes to passwords.
6. Verifiers should limit the number of failed authentication attempts and lock out potential adversaries.

### 2FA or MFA
There are three components of multi-factor authentication.
1. Knowledge: Something only you know.
2. Possession: An item or device only possessed by an authorized user.
3. Inheritance: Only a factor you could obtain, like your fingerprint, face, or other bio metrics.

### Single Sign-On (SSO)
Since so many different services have different password rules and reusing passwords is unsafe, Single Sign-On (SSO) lets you log into multiple third-party services using one secure account (like Google or Facebook). This reduces hassle and improves security by centralizing authentication.

### Password Managers
A **password manager** securely stores complex passwords so you don’t have to memorize them. It can detect phishing sites and works across multiple services, unlike basic browser saving. The main risk is that all passwords depend on one master password for access.

### Passkey
**Passkeys** are a new technology that use cryptography with a **public–private key pair** to let you log in without typing a password. The public key stays with the service, and the private key stays securely on your device.