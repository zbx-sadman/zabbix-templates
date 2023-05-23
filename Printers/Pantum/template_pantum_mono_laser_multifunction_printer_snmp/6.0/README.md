### Pantum mono laser multifunction printer

## Overview

SNMPv2 template is made by reverse engineering way.

Zhuhai Pantum Technology as an Pantum trademark owner does not provide private MIB-file for its products, therefore templates can contain errors, and Zabbix items can points to wrong/obsolete OIDs. Some Pantum devices or firmware releases does not support full OID set, therefore several metrics can be unavialable.

Tested on:
 - M6700DW / FW 3.A.0.3;
 - M7100DW / FW 2.A.1.3 (full compatibility found);
 - M7100DN / FW 3.6.1.4 (partial compatibility found).

## Setup

Just import template.

## Macros used

| Name                           | Description                                          |
|:-------------------------------|:-----------------------------------------------------|
| {$CARTRIDGE.RESOURCE.MIN.WARN} | Low warning level of cartridge resource (toner)      |
| {$CARTRIDGE.RESOURCE.MIN.CRIT} | Low critical level of cartridge resource (toner)     |
| {$CARTRIDGE.WEAR.PER.HOUR.MAX} | Trigger's threshold for cartridge wearing (per hour) |
| {$PAGES.PRINTED.PER.HOUR.MAX}  | Trigger's threshold for printed pages (per hour)     |
| {$DRUM.RESOURCE.MIN.WARN}      | Low warning level of drum unit resource              |
| {$DRUM.RESOURCE.MIN.CRIT}      | Low critical level of drum unit resource             |
| {$SNMP.TIMEOUT}                | Used for "SNMP agent availability" metric            |

## Discovery rules

Extended statistic discovery - Create items for extended statistic metrics: Cartridge / Drum unit models, s/n, resource

## Items collected

| Name                          | Description |    Type         | Key and additional info                         |
|:------------------------------|:-----------:|:----------------|-------------------------------------------------|
| Cartridge prints total        |      -      | SNMP agent      | printer.cartridge.total_prints                  |
| Cartridge status              |      -      | SNMP agent      | printer.cartridge.status                        |
| Cartridge wearing (per hour)  |      -      | Calculated      | printer.cartridge.wear_per_hour                 |
| Catrirdge resource (%)        |      -      | SNMP agent      | printer.cartridge.resource                      |
| Drum status                   |      -      | SNMP agent      | printer.drum.status                             |
| Firmware version              |      -      | SNMP agent      | system.fw.version                               |
| Front cover status            |      -      | SNMP agent      | system.hw.front_cover_status                    |
| Hardware model name           |      -      | SNMP agent      | system.hw.model                                 |
| Hardware production date      |      -      | SNMP agent      | system.hw.production_date                       |
| Hardware serial number        |      -      | SNMP agent      | system.hw.serial_number                         |
| Memory size                   |      -      | SNMP agent      | system.hw.total_memory                          |
| Pages printed (per hour)      |      -      | Calculated      | printer.page.printed_per_hour                   |
| Pages printed on A4           |      -      | SNMP agent      | printer.page.printed_a4                         |
| Pages printed on auto-duplex  |      -      | SNMP agent      | printer.page.printed_duplex                     |
| Pages printed on other size   |      -      | SNMP agent      | printer.page.printed_others                     |
| Pages printed total           |      -      | SNMP agent      | printer.page.printed_total                      |
| Papier status                 |      -      | SNMP agent      | printer.papier_status                           |
| Printer status                |      -      | SNMP agent      | printer.status                                  |
| Sleep time                    |      -      | SNMP agent      | system.hw.sleep_time                            |
| SNMP agent availability       |      -      | Zabbix internal | zabbix[host,snmp,available]                     |
| System state                  |      -      | SNMP agent      | system.state                                    |
| Cartridge model\*             |      -      | SNMP agent      | printer.cartridge.model[extended]               |
| Cartridge s/n\*	        |      -      | SNMP agent      | printer.cartridge.serial_number[extended]       |
| Drum model\*	                |      -      | SNMP agent      | printer.drum.model[extended]                    |
| Drum s/n\*	                |      -      | SNMP agent      | printer.drum.serial_number[extended]            |
| Drum resource (%)\*	        |      -      | SNMP agent      | printer.drum.resource[extended]                 |

\* Available on printers/firmware with SNMP subtree 1.3.6.1.4.1.40093.10 exists

## Triggers

| Name                               | Severity     |
|:-----------------------------------|:-------------|
| No cartridge installed             | High         |
| No drum unit installed             | High         |
| Front cover opened                 | Warning      |
| No SNMP data collection            | High         |
| Cartridge resource is critical low | Average      |
| Cartridge resource is low          | Warning      |
| No papier on feeder                | Information  |
| Cartridge weared too fast          | Warning      |
| Page printed too fast              | Warning      |
| Firmware has changed               | Information  |
| Cartridge has changed\*            | Information  |
| Drum has changed\*                 | Information  |
| Drum resource is low\*             | Warning      |
| Drum resource is critical low\*    | Warning      |

\* Available on printers/firmware with SNMP subtree 1.3.6.1.4.1.40093.10 exists

## Feedback

e-mail to me: zbx.sadman@gmail.com

## Demo

![image](https://github.com/zbx-sadman/zabbix-templates/assets/12827470/747d593b-ba22-4c82-9b2c-2417ae800cf0)

