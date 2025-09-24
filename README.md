# task1-port-scanning
Host: 172.20.10.5
Discovered ports:
- 22/tcp open ssh (OpenSSH 8.2p1)
- 80/tcp open http (Apache httpd 2.4.41)
- 445/tcp open smb (microsoft-ds)


Risk assessment:
- SSH (22): medium risk if password auth enabled. Recommend key-based auth + disable password login and rate-limiting.
- HTTP (80): check web server and any CMS for updates. Use HTTPS + HSTS if serving web pages.
- SMB (445): high risk if exposed — restrict access to LAN or specific IPs, patch OS.


Remediation actions:
1. Disable unnecessary services or stop them if not required:
2. Patch services & OS (apply vendor updates).
3. Implement firewall rules to restrict access:
4. Use stronger authentication (SSH keys + passphrases, MFA for remote access).
5. Place management intaces behind VPN where feasible.


Notes:
- Confirm services are expected before shutting them down.
- Re-scan after applying fixes to verify closed ports.
