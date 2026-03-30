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
* static_ip: 192.168.10.5, gateway: 192.168.10.1

TODO:
* Jos klooni ei hyvä, tee itse atomeista! kupari- tai messinkiputkeen, epoksivalu
