# Command-Cheat-Sheet
Used for personal quick homelabs diagnosis. (Personal use only)

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
