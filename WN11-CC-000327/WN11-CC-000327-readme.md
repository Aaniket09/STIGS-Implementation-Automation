# STIG ID: WN11-CC-000327

## 🛡️ Vulnerability Description
**PowerShell Transcription must be enabled.**

While logging captures individual commands, Transcription creates a comprehensive text-based record of the entire PowerShell session, including input and output. Failure to enable this creates a gap in forensic analysis, making it difficult to reconstruct an attacker's actions during an intrusion.

---

## ⚙️ Remediation Strategy

**PowerShell Implementation Logic:**
The automation script modifies the Registry to turn on system-wide transcription and define a secure storage location.

1.  **Registry Configuration:** The script targets `HKLM\SOFTWARE\Policies\Microsoft\Windows\PowerShell\Transcription`.
2.  **Activation:** It sets the `EnableTranscription` DWORD value to `1`.
3.  **Output Definition (Optional but Recommended):** The script may also configure the `OutputDirectory` string to ensure logs are saved to a hardened, monitored directory rather than the user's default documents folder.

[Link to Remediation Script](PLACEHOLDER_LINK_HERE)

---

## 📊 Rescan Verification Report

![Rescan Result - WN11-CC-000327](PLACEHOLDER_IMAGE_LINK_HERE)