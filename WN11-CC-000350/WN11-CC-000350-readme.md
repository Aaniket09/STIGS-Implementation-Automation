# STIG ID: WN11-CC-000350

## 🛡️ Vulnerability Description
**The WinRM service must not allow unencrypted traffic.**

Allowing unencrypted traffic on the WinRM service exposes administrative commands and data to interception. Attackers performing Man-in-the-Middle (MITM) attacks can sniff this traffic to gain insight into the environment or inject malicious commands into the management session.

---

## ⚙️ Remediation Strategy

**PowerShell Implementation Logic:**
This remediation utilizes the WSMan provider to harden the transport layer of remote management.

1.  **WSMan Configuration:** The script targets the service configuration at `WSMan:\localhost\Service`.
2.  **Attribute Modification:** It locates the `AllowUnencrypted` attribute.
3.  **Enforcement:** The script sets this value to `$false`. This ensures that the service rejects any connection attempts that do not utilize transport layer encryption (HTTPS).

[Link to Remediation Script](PLACEHOLDER_LINK_HERE)

---

## 📊 Rescan Verification Report

![Rescan Result - WN11-CC-000350](PLACEHOLDER_IMAGE_LINK_HERE)