# [Windows Fundamentals](https://tryhackme.com/room/windowsfundamentals3xzx)

## What I Learned

Today I focused on Windows Fundamentals and explored several built-in Windows security features.

### 1. Windows Update

Windows Update is a Microsoft service that provides:

* Security updates
* Feature updates
* Improvements
* Patches for the Windows operating system

Microsoft's regular security updates are released on the **second Tuesday of each month**, commonly referred to as **Patch Tuesday**.

Windows Update can be accessed through Settings or from Command Prompt using:

`control /name Microsoft.WindowsUpdate`

### 2. Windows Security

Windows Security provides a central location for managing several security protections.

The major protection areas I studied were:

* Virus & Threat Protection
* Firewall & Network Protection
* App & Browser Control
* Device Security

Windows Security also uses status indicators:

* **Green:** Device is sufficiently protected
* **Yellow:** A security recommendation requires review
* **Red:** A warning requires immediate attention

### 3. Virus & Threat Protection

I learned how this section can be used to monitor for threats and scan files and folders for potentially harmful software.

### 4. Firewall & Network Protection

I learned how Windows Firewall helps control network traffic and protect a device from unwanted connections. 

Windows Firewall offers three firewall principles:

* Domain Network: The domain principle applies to network where the host system can authenticate to a domain controller.
* Private Network: A user-assigned profile and is used to designate private or home address.
* Public Network: Used to designate public addresses such as Wi-Fi hotspots.

### 5. App & Browser Control

Windows Defender Smart Screen provides protection against potentially malicious applications, files and websites.

Exploit protection is built into Windows 10 to help protect your device against attacks.

### 6. Device Security

I learned about Windows security features designed to protect the device at a deeper hardware and firmware level.

### 7. BitLocker

BitLocker provides volume encryption to help protect data from unauthorized access if a device is lost, stolen or improperly decommissioned.

On devices that TPM (Trusted Platform Module) is installed, Bitlocker offers the best protection.

`TPM is a secure cypto processor that is designed to carry out cryptographic operations in order to provide hardware-based, security-related functions.`

Also look up [BitLocker Overview](https://learn.microsoft.com/en-us/windows/security/operating-system-security/data-protection/bitlocker/)

### 8. Volume Shadow Copy Service (VSS)

VSS creates copies that can assist with file and system recovery.

One important security lesson I learned is that malware and ransomware can attempt to locate and delete recovery copies, making recovery more difficult after an attack.

This reinforced the importance of having reliable backups rather than depending entirely on recovery mechanisms stored on the same system.

VSS can be accessed from Command Prompt using:

`vssadmin`

## Key Takeaway

Windows has several security mechanisms working at different layers — from updates and malware protection to firewalls, encryption, device security and recovery.

Understanding these individual features contribute to a broader defensive security strategy.

---
