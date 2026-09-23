# NoktiData 📚

Centralized data repository for **Nokti**, the university grade-calculation application.

NoktiData separates standard academic curriculum and localization data from the Flutter application so compatible data changes can be delivered without publishing a new APK.

## 🎯 Purpose

This repository contains only shared application data:
- Standard LMD curriculum
- English translations
- Arabic translations
- French translations

It must **not** contain personal student data.

## 📁 Repository Structure

- `curriculum/system.json` — standard academic curriculum
- `lang/en.json` — English translations
- `lang/ar.json` — Arabic translations
- `lang/fr.json` — French translations

## 🔗 Raw Data Endpoints

These files are consumed directly by Nokti through GitHub Raw.

| Data | Raw URL |
|---|---|
| Curriculum | https://raw.githubusercontent.com/MohamedBabaamer/NoktiData/main/curriculum/system.json |
| English | https://raw.githubusercontent.com/MohamedBabaamer/NoktiData/main/lang/en.json |
| Arabic | https://raw.githubusercontent.com/MohamedBabaamer/NoktiData/main/lang/ar.json |
| French | https://raw.githubusercontent.com/MohamedBabaamer/NoktiData/main/lang/fr.json |

Nokti application: https://github.com/MohamedBabaamer/nokti-app

## 🔄 How Updates Reach Nokti

The application uses this fallback order:

1. GitHub Raw (latest NoktiData)
2. SharedPreferences cache
3. Bundled JSON asset inside the APK

A successful update to the `main` branch can therefore become available to the application without rebuilding the APK.

Users can also trigger a curriculum refresh from Nokti's synchronization controls.

## ✅ Data Compatibility Rules

### 1. Keep JSON valid
Every change must remain valid JSON.

### 2. Preserve existing schemas
Do not rename, remove, or restructure fields used by released Nokti clients unless the application has been updated to support the change.

### 3. Preserve translation keys
When adding a localization key, add it to all three language files and keep their key sets synchronized.

### 4. Do not store personal data
Never commit student grades, backups, settings, user profiles, personal identifiers, or device-specific state.

### 5. Review curriculum changes carefully
Curriculum edits can affect grade calculations. Verify course names, coefficients, credits, semester placement, Teaching Unit placement, and grading rules.

## 🧪 Recommended Change Workflow

Edit JSON → Validate JSON → Review diff → Commit to main → Open Nokti → Refresh / Force Sync → Verify the new data.

For important changes, test the corresponding Nokti screens and calculations before distributing a new APK.

## 📝 Versioning

NoktiData does not need a separate APK release for every curriculum or translation edit.

The current application release using this repository is **Nokti v1.2.0**.

The repository currently has no separate GitHub Release; data changes are delivered from the `main` branch through the Raw endpoints.

## 🔐 Privacy

NoktiData is intentionally limited to shared application data. Personal academic records are stored by the Nokti application locally on the user's device and are not meant to be uploaded to this repository.

## 🤝 Related Project

**Nokti Flutter App** — https://github.com/MohamedBabaamer/nokti-app

## 📄 Maintenance Rule

Treat the JSON structure as a compatibility contract with released Nokti clients.

**Preserve the schema, validate the data, and avoid breaking existing keys.**