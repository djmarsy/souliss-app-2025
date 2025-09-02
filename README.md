# SoulissApp Next (Android, 2025)

Base moderna (Kotlin + Jetpack Compose) per controllare nodi Souliss in LAN.

## Prerequisiti
- Android Studio Koala o superiore (JDK 17 incluso) **oppure** Gradle 8.6+

## Build rapida (debug)
```bash
./gradlew :app:installDebug
```

## APK release firmato (locale)
1) Crea un keystore:
```bash
keytool -genkeypair -alias soulissapp -keyalg RSA -keysize 4096 -validity 36500 -keystore keystore.jks
```
2) Imposta le password in `gradle.properties`
3) Costruisci:
```bash
./gradlew :app:assembleRelease
```
4) APK: `app/build/outputs/apk/release/app-universal-release.apk`

## GitHub Actions (consigliato)
- Aggiungi i secrets: `KESTORE_BASE64`, `STORE_PASSWORD`, `KEY_PASSWORD`, `KEY_ALIAS`
- Esegui il workflow **Android Release APK** e scarica l'artefatto.
