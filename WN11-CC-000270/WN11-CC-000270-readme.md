# STIG ID: WN11-CC-000270

## 🛡️ Vulnerability Description
**The RDP client must be prevented from saving passwords.**

If a user saves their credentials in the Remote Desktop Connection client, those credentials are stored on the disk. If an attacker compromises the machine, they can harvest these saved connections to pivot laterally to other servers without needing to crack a password.

---

## ⚙️ Remediation Strategy

**PowerShell Implementation Logic:**
The script applies a Group Policy restriction via the Registry to disable the "Save Credentials" checkbox in RDP.

1.  **Registry Key Check:** The script looks for `HKLM\SOFTWARE\Policies\Microsoft\Windows NT\Terminal Services`. It creates the key if missing.
2.  **Policy Application:** It targets the value `DisablePasswordSaving`.
3.  **Modification:** The script sets this DWORD to `1`. This greys out the option to save passwords in the RDP client UI and prevents the underlying functionality.

[Link to Remediation Script](PLACEHOLDER_LINK_HERE)

---

## 📊 Rescan Verification Report

![Rescan Result - WN11-CC-000270](PLACEHOLDER_IMAGE_LINK_HERE)