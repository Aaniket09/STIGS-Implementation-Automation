# STIG ID: WN11-SO-000120

## 🛡️ Vulnerability Description
**The SMB server must always perform SMB packet signing.**

SMB packet signing places a digital signature on every packet in the SMB stream. This verifies the origin and authenticity of the data. Without this enforced on the server side, the system is vulnerable to SMB Relay attacks, where an attacker intercepts traffic and relays it to another system to gain unauthorized access.

---

## ⚙️ Remediation Strategy

**PowerShell Implementation Logic:**
The script modifies the "LanManServer" (Server service) parameters in the registry.

1.  **Registry Targeting:** The script navigates to `HKLM\System\CurrentControlSet\Services\LanManServer\Parameters`.
2.  **Signature Enforcement:** It identifies the `RequireSecuritySignature` value.
3.  **Value Update:** The script sets this DWORD to `1`. This mandates that any client attempting to connect to this machine via SMB must support and use packet signing, or the connection is dropped.

[Link to Remediation Script](PLACEHOLDER_LINK_HERE)

---

## 📊 Rescan Verification Report

![Rescan Result - WN11-SO-000120](PLACEHOLDER_IMAGE_LINK_HERE)