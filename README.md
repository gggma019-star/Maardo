# Shop Manager

Android app for managing a shop: products, stock, sales, and shop settings.

## Tech stack

- Kotlin
- Jetpack Compose (Material 3)
- MVVM (ViewModel + repository, StateFlow)
- Min SDK 26 (Android 8.0), target/compile SDK 35
- Package: `com.shopmanager`

## Project structure

```
shop-manager/
├── app/
│   └── src/main/java/com/shopmanager/
│       ├── data/          # models + repositories (in-memory products/sales, SharedPreferences settings)
│       ├── viewmodel/     # ShopViewModel
│       └── ui/
│           ├── components/
│           ├── navigation/
│           ├── screens/   # Dashboard, Products, Sales, Settings
│           └── theme/
├── gradle/
├── .gitignore
├── build.gradle.kts
├── settings.gradle.kts
└── gradle.properties
```

## Features

- Dashboard: today's sales, profit, orders, and product count
- Products: add/edit products with image, category, buying/selling price, stock
- Sales: record sales with live stock before/after summary
- Settings: shop name, logo, contact info, currency, and theme — persisted in SharedPreferences

## Build

Open the folder in Android Studio and let it generate the Gradle wrapper, then run `app`.

> Products and sales currently live in memory and reset when the app closes; settings persist via SharedPreferences. Swap `ShopRepository` for Room/SQLite for durable product/sales storage.
