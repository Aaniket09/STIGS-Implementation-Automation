# STIG ID: WN11-CC-000345

## 🛡️ Vulnerability Description
**The WinRM service must not use Basic authentication.**

Basic authentication sends user credentials across the network in an easily reversible Base64 format. If an attacker intercepts this traffic, they can decode the credentials instantly. Disabling Basic authentication forces the use of stronger, encrypted protocols like Kerberos or Negotiate.

---

## ⚙️ Remediation Strategy

**PowerShell Implementation Logic:**
Unlike registry keys, WinRM is best managed via the WSMan (Web Services for Management) drive provider in PowerShell.

1.  **WSMan Provider Access:** The script accesses the `WSMan:\localhost\Service\Auth` path.
2.  **Configuration Change:** It targets the `Basic` setting item.
3.  **Enforcement:** The script sets the value to `$false`. This creates a hard block preventing the Windows Remote Management service from accepting credentials presented via Basic Auth.

[Link to Remediation Script](PLACEHOLDER_LINK_HERE)

---

## 📊 Rescan Verification Report

![Rescan Result - WN11-CC-000345](PLACEHOLDER_IMAGE_LINK_HERE)