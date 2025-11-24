# STIG ID: WN11-CC-000310

## 🛡️ Vulnerability Description
**Users must be prevented from changing installation options.**

Allowing users to change installation options (such as location, feature sets, or elevated privileges) during software setup can bypass security controls. It creates an opportunity for malware or malicious insiders to install software in unauthorized directories or with insecure configurations.

---

## ⚙️ Remediation Strategy

**PowerShell Implementation Logic:**
The script locks down the Windows Installer behavior via the Registry.

1.  **Registry Targeting:** The script navigates to `HKLM\Software\Policies\Microsoft\Windows\Installer`.
2.  **Control Restriction:** It targets the `EnableUserControl` value.
3.  **Modification:** The script sets this DWORD to `0`. This restricts the Windows Installer, preventing users from changing install parameters and forcing the installer to use the default, admin-approved settings.

[Link to Remediation Script](PLACEHOLDER_LINK_HERE)

---

## 📊 Rescan Verification Report

![Rescan Result - WN11-CC-000310](PLACEHOLDER_IMAGE_LINK_HERE)