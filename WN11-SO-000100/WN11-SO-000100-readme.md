# STIG ID: WN11-SO-000100

## 🛡️ Vulnerability Description
**The SMB client must always perform SMB packet signing.**

Similar to the server-side requirement, the client (the Windows 11 machine itself) must verify the authenticity of the servers it connects to. If disabled, the client can be tricked into connecting to a rogue SMB server set up by an attacker, leading to credential theft or the delivery of malicious payloads.

---

## ⚙️ Remediation Strategy

**PowerShell Implementation Logic:**
The script modifies the "LanmanWorkstation" (Workstation service) parameters in the registry.

1.  **Registry Targeting:** The script navigates to `HKLM\System\CurrentControlSet\Services\LanmanWorkstation\Parameters`.
2.  **Signature Enforcement:** It identifies the `RequireSecuritySignature` value.
3.  **Value Update:** The script sets this DWORD to `1`. This prevents the Windows 11 client from establishing connections to file shares that do not support packet signing.

[Link to Remediation Script](PLACEHOLDER_LINK_HERE)

---

## 📊 Rescan Verification Report

![Rescan Result - WN11-SO-000100](PLACEHOLDER_IMAGE_LINK_HERE)