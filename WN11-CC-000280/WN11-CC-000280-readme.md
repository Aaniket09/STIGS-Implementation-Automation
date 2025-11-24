# STIG ID: WN11-CC-000280

## 🛡️ Vulnerability Description
**The Remote Desktop Session Host must be configured to always prompt for a password upon connection.**

Even if a user has valid credentials, automated malware or an attacker using a hijacked session might try to initiate an RDP connection automatically. Enforcing a password prompt ensures that a human is present and verifies their identity before the session is fully established.

---

## ⚙️ Remediation Strategy

**PowerShell Implementation Logic:**
The script enforces the "Always prompt for password" policy via the Terminal Services registry key.

1.  **Registry Targeting:** The script accesses `HKLM\SOFTWARE\Policies\Microsoft\Windows NT\Terminal Services`.
2.  **Flag Configuration:** It identifies the value `fPromptForPassword`.
3.  **Enforcement:** The script sets this DWORD to `1`. This overrides any saved credentials or auto-login settings, forcing the Windows login screen to appear every time an RDP session connects.

[Link to Remediation Script](PLACEHOLDER_LINK_HERE)

---

## 📊 Rescan Verification Report

![Rescan Result - WN11-CC-000280](PLACEHOLDER_IMAGE_LINK_HERE)