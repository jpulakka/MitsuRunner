Fork of https://github.com/VeliML/MitsuRunner for my personal purposes.

Forked @ 5a3b6a710bb67ec6126cdbba63bb3e158a04b7e6 = https://github.com/VeliML/MitsuRunner/releases/tag/2026_1 + license file addition

https://lampopumput.info/foorumi/threads/msz-ln-sulatushuijaus.31223/page-63

---

* C:\CODE\elektro\mitsurunner\ asennettu python -m venv .\
* pip3 install esphome -U ajettu, CH340-ajuri asennettu, esphome versiota 2026.3.0
* C:\CODE\elektro\mitsurunner\counterfeit_DS18B20_esp8266\
* C:\CODE\elektro\mitsurunner\MitsuRunner\
* Scripts\activate = aktivoi venv
* hw_check.yaml testaa (esphome run hw_check.yaml) -> Dallas D2, Relay D1
* esphome run mitsu_conf.yaml
  * Tämä toimii nyt myös OTA.
* In Home Assistant, go to Settings → Devices & Services, click "Add Integration", choose ESPHome, enter MitsuRunner’s hostname or IP, and complete the wizard.
* https://esphome.io/components/ota/esphome/
* https://web.esphome.io/
* static_ip: 192.168.10.5, gateway: 192.168.10.1, fallback ap: 192.168.4.1

TODO:
* Jos klooni ei hyvä, tee itse atomeista! kupari- tai messinkiputkeen, epoksivalu

Usage:
1. cd C:\CODE\elektro\mitsurunner\
2. Scripts\activate
3. cd MitsuRunner
4. Edit secrets.yaml, replace PASSWORD
5. esphome run mitsu_conf.yaml

Reboot issues: After the next spontaneous crash, run esphome logs mitsu_conf.yaml right after it comes back — the 2026.4 crash handler will print a decoded backtrace in the boot log automatically.
* Also, look at Reset Reason. If it's Software Watchdog, watch Free Heap and Loop Time trends leading up to it — the HA history graph is useful here.
* If Free Heap is the culprit, the known fix for ESP8266 long-uptime stability is periodic scheduled reboots (e.g., every 7 days at 03:00 via time + App.restart()), since the root cause is usually the closed-source WiFi SDK.
* 5/2026 käännetty esphome 2026.4.5:llä, toistaiseksi vaikuttaa vakaalta, >5000 minuutissa 1 lukuvirhe outdoor sensorilta, ei muuta -> Mutta kaatui pian sen jälkeen.
* Korjausyritys https://github.com/jpulakka/MitsuRunner/commit/3ce0486891a9600c6d4f8acfb47eb55286507ef2 + https://github.com/jpulakka/MitsuRunner/commit/2d2b59bb734ce93f23897921af4234ec60e39883 tästä PR jos hyvä. Tosin power_save_mode: none on redundantti, se on jo defaulttina niin esp8266:ssa.
* post_connect_roaming: false oli katastrofi. Mutta toisen wifin poistaminen listasta näyttää  hyvältä, nyt on taas stable.
* TODO ehkä: float formatting fixes, were those just artifacts in stack trace, not reasons?

