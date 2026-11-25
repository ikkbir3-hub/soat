# Электрон соат: APK лойиҳаси

## 1-усул: GitHub Actions (компьютерга ҳеч нарса ўрнатмасдан)

1. github.com да янги репозиторий яратинг.
2. Шу папкадаги барча файлларни (`.github` папкаси билан) репозиторийга юкланг.
3. Репозиторийда **Actions** бўлимига ўтинг. «APK йиғиш» жараёни ўзи ишга тушади (2-5 дақиқа).
4. Тугагач, жараённи очиб, пастдаги **Artifacts** бўлимидан `elektron-soat-apk` ни юклаб олинг.
5. Зип ичидаги `app-debug.apk` ни телефонга ўтказиб ўрнатинг («Номаълум манбалардан ўрнатиш»га рухсат керак).

## 2-усул: Компьютерда

Керак: Node.js 22+, Java 21, Android Studio.

```bash
npm install
npx cap add android
npx @capacitor/assets generate --android
npx cap sync android
npx cap open android      # Android Studio очилади: Build → Build APK(s)
```

## Ўзгартириш

- Соат кодини `www/index.html` да таҳрирланг.
- Илова номи ва ID: `capacitor.config.json` (`appId` ни ўзингизникига алмаштиринг).
- Иконка: `assets/` папкасидаги PNG файллар.
- Веб файлни ўзгартиргач: `npx cap sync android`.

## Play Market учун

Debug APK фақат шахсий фойдаланиш учун. Play Market учун imzolangan release AAB керак:
Android Studio → Build → Generate Signed Bundle.
