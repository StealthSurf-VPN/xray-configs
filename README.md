# StealthSurf Server Configs

Public configuration templates used by StealthSurf on hosted servers.

This repository contains the config set from main backend: base Xray profiles, location-specific overrides, extended protocol configs, Hysteria2 routing rules, AmneziaWG templates, and MTProto/telemt configuration templates.

The goal of this repository is transparency: it shows which server-side settings are used in production-like infrastructure, including DNS behavior, routing rules, inbound/outbound profiles, Reality/VLESS/Trojan/Shadowsocks/Outline settings, Hysteria2 rules, AmneziaWG parameters, and MTProto proxy settings.

## Contents

- `default.json` — the base configuration of Xray for servers that do not have their own configuration by location.
- `{location_id}.json` — location-specific Xray overrides.
- `extended-*-vless.json` — extended VLESS configurations.
- `extended-*-trojan.json` — extended Trojan configurations.
- `extended-*-shadowsocks.json` — extended Shadowsocks 2022 configurations.
- `extended-*-outline.json` — extended Outline configurations.
- `default-hysteria.json` and `*-hysteria.json` — Hysteria2 routing and rule sets.
- `amnezia-*.json` — AmneziaWG configuration templates.
- `telemt-*.toml` — MTProto/telemt configuration templates.
- `hysteria-reject-rules.json` — Hysteria2 reject rules.

## Location IDs

Some files are named by internal `location_id`. These IDs map to StealthSurf server locations:

| ID | Code | Location |
| --- | --- | --- |
| 1 | FI | Finland |
| 2 | NL | Netherlands |
| 3 | US | United States |
| 4 | DE | Germany |
| 5 | UK | United Kingdom |
| 6 | FR | France |
| 7 | SE | Sweden |
| 8 | MD | Moldova |
| 9 | PL | Poland |
| 10 | TR | Turkey |
| 11 | BR | Brazil |
| 12 | RU | Russia |
| 13 | JP | Japan |
| 14 | HK | Hong Kong |
| 15 | CA | Canada |
| 16 | IT | Italy |
| 17 | KZ | Kazakhstan |
| 18 | RB | Smart Location |
| 19 | KR | South Korea |
| 20 | AU | Australia |
| 21 | AL | Albania |
| 22 | RB | Smart Location East |
| 23 | CH | Switzerland |
| 24 | IE | Ireland |
| 25 | LT | Lithuania |
| 26 | NO | Norway |
| 27 | IN | India |
| 28 | AE | United Arab Emirates |
| 29 | RU | Russia Gaming |
| 30 | FI | Finland |
| 31 | RB | Smart Location SPB |
| 32 | KZ | Kazakhstan |
| 33 | CZ | Czech Republic |
| 34 | BY | Belarus |
| 35 | RB | Singapore |
| 36 | SG | Smart Location (#2) |

## Notes

Several locations are virtual locations: traffic is served from NL infrastructure while the advertised IP geolocation may point to another country.

Files may contain placeholders such as `__PUBLIC_HOST__`, `__TELEMT_AUTH_TOKEN__`, or `__SYSTEM_SECRET__`. These are not real secrets and are replaced during deployment.

This repository is intended for review, documentation, and transparency. It is not a complete standalone deployment package.