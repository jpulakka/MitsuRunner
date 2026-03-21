Fork of https://github.com/VeliML/MitsuRunner for my personal purposes.

Forked @ 5a3b6a710bb67ec6126cdbba63bb3e158a04b7e6 = https://github.com/VeliML/MitsuRunner/releases/tag/2026_1 + license file addition

https://lampopumput.info/foorumi/threads/msz-ln-sulatushuijaus.31223/page-63

---

* C:\CODE\elektro\mitsurunner\ asennettu python -m venv .\
* pip3 install esphome -U ajettu, CH340-ajuri asennettu, esphome versiota 2026.3.0
* C:\CODE\elektro\mitsurunner\counterfeit_DS18B20_esp8266\
* C:\CODE\elektro\mitsurunner\MitsuRunner\
* Scripts\activate = aktivoi venv

OTA:
* https://esphome.io/components/ota/esphome/
* https://web.esphome.io/

TODO:
* hw_check.yaml testaa (esphome run hw_check.yaml) - Toimiko tämä Dallas D3, Relay D1? Ei kai
* mitsu_conf.yaml säädä dependencyt:
  * platform_wemos.yaml
    * HomeAssistant_API käytettäessä ota käyttöön HomeAssistant api.  MQTT HASSiin
  * secrets.yaml
  * dallas_hub.yaml
  * mqtt_local.yaml
* Sitten: esphome run mitsu_conf.yaml
* Jos klooni ei hyvä, tee itse atomeista! kupari- tai messinkiputkeen, epoksivalu
* yhteinen 10 mm läpivienti kolmelle johdolle?