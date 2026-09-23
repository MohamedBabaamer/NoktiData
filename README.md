# NoktiData

Centralized public data repository for the Nokti academic calculator.

## Structure

- `curriculum/system.json` — standard academic curriculum
- `lang/en.json` — English UI translations
- `lang/ar.json` — Arabic UI translations
- `lang/fr.json` — French UI translations

## Source

This repository is the shared data source for Nokti clients.

- Flutter app: https://github.com/MohamedBabaamer/nokti-app

## Raw URLs

Curriculum:

https://raw.githubusercontent.com/MohamedBabaamer/NoktiData/main/curriculum/system.json

English:

https://raw.githubusercontent.com/MohamedBabaamer/NoktiData/main/lang/en.json

Arabic:

https://raw.githubusercontent.com/MohamedBabaamer/NoktiData/main/lang/ar.json

French:

https://raw.githubusercontent.com/MohamedBabaamer/NoktiData/main/lang/fr.json

## Rule

Keep the existing JSON schemas backward compatible with Nokti clients.
Do not store user grades, backups, settings, or other personal data here.
