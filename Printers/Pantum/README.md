## Zabbix templates for Pantum multifunction printer

Note: Zhuhai Pantum Technology as an Pantum trademark owner does not provide private MIB-file for its products. This templates is made by reverse engineering way, and can contain errors, Zabbix items can points to wrong/obsolete OIDs. Some Pantum devices or firmware releases does not support full OID set, therefore  several template's items can going to unsupported state.

Please, let me know, if errors found on the template.

Production environment: Zabbix 6.0 LTS, SNMPv2.

Templates list:
- [template_pantum_m6700dw_snmp.xml]( https://raw.githubusercontent.com/zbx-sadman/zabbix-templates/main/Printers/Pantum/template_pantum_m6700dw_snmp.xml) - M6700DW mono laser multifunction printer, tested on M6700DW (FW 3.A.0.3). Also tested on M7100DW/2.A.1.3 (full compatibility found), and M7100DN/3.6.1.4 (partial compatibility found).

With this template you can get cartridge/drum unit model/serial number/resource in percent, printed page counter, see system state, detect errors, and more information.

![image](https://github.com/zbx-sadman/zabbix-templates/assets/12827470/747d593b-ba22-4c82-9b2c-2417ae800cf0)
