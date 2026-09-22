# Command-Cheat-Sheet
Used for personal quick home lab diagnosis. (Personal use only)

# Network diagnostics
* ipconfig /all — full adapter config: IP, subnet, gateway, DNS, MAC, DHCP lease
* ipconfig /release then ipconfig /renew — force a new DHCP lease
* ipconfig /flushdns — clear cached DNS (fixes stale or wrong sites loading)
* ping <host> / ping -t <host> — reachability check / continuous ping to catch intermittent drops
* tracert <host> — shows every hop to the destination and where it breaks
* pathping <host> — like tracert but runs longer and gives per-hop packet loss %
* nslookup <domain> — checks what IP a domain resolves to, tests the DNS server directly
* netstat -ano — active connections and listening ports with PID, pair with Task Manager to find what owns a port
* arp -a — ARP cache, MAC-to-IP mappings on the local segment
* netsh wlan show interfaces — signal strength, channel, current SSID
* netsh winsock reset / netsh int ip reset — resets Winsock / full TCP-IP stack, the fix for stubborn "no internet" after malware or VPN     weirdness
* Test-NetConnection <host> -Port 443 (PowerShell) — modern combined ping + port check

# System info & health
* systeminfo — OS build, install date, hotfixes, memory, boot time; good first command on an unfamiliar machine
* dxdiag — DirectX/GPU/sound diagnostics for display or audio issues
* Get-ComputerInfo (PowerShell) — same idea as systeminfo, structured output
* winver — quick OS version/build check

# Disk & file system
* sfc /scannow — scans and repairs corrupted system files
* DISM /Online /Cleanup-Image /RestoreHealth — repairs the Windows image itself; run before sfc if sfc can't fix something
* chkdsk C: /f /r — checks and repairs disk errors/bad sectors, needs a reboot on the system drive
* Get-PhysicalDisk (PowerShell) — disk health status, catches a failing drive early
* cleanmgr — Disk Cleanup GUI when space is the problem
