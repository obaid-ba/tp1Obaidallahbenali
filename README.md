# TP1 — Compteur Android

Application Android simple réalisée en **Kotlin** dans le cadre du TP1.
Elle affiche un compteur que l'on peut **incrémenter**, **décrémenter** et **réinitialiser** à l'aide de trois boutons.

**Auteur :** Obaidallah Ben Ali

---

## Fonctionnalités

| Bouton | Action |
|---|---|
| **+** | Ajoute 1 au compteur |
| **−** | Retire 1 au compteur (les valeurs négatives sont autorisées) |
| **Réinitialiser** | Remet le compteur à 0 |

La valeur courante est affichée en grand au centre de l'écran.

## Captures d'écran

| Écran initial | Après incrémentation | Après décrémentation |
|:---:|:---:|:---:|
| ![Écran initial](screenshots/initial.png) | ![Incrémentation](screenshots/increment.png) | ![Décrémentation](screenshots/decrement.png) |

## Technologies

- **Langage :** Kotlin
- **Interface :** XML (Views) avec `ConstraintLayout`
- **Activité :** `AppCompatActivity`
- **Build :** Gradle (Kotlin DSL) — Android Gradle Plugin 9.0.1
- **SDK :** `minSdk 24` (Android 7.0) — `targetSdk / compileSdk 36`

## Structure du projet

```
app/src/main/
├── AndroidManifest.xml
├── java/com/example/compteurandroid/
│   └── MainActivity.kt        # Logique du compteur
└── res/
    ├── layout/
    │   └── activity_main.xml  # Interface (titre, compteur, 3 boutons)
    └── values/                # Couleurs, chaînes, thèmes
```

## Fonctionnement

Dans `MainActivity.kt`, une variable `compteur` garde la valeur courante.
Chaque bouton possède un `setOnClickListener` qui modifie cette variable puis met à jour le `TextView` :

```kotlin
buttonIncrementer.setOnClickListener {
    compteur++
    textViewCompteur.text = compteur.toString()
}
```

## Lancer le projet

1. Cloner le dépôt :
   ```bash
   git clone https://github.com/obaid-ba/tp1Obaidallahbenali.git
   ```
2. Ouvrir le dossier dans **Android Studio**.
3. Attendre la synchronisation Gradle.
4. Lancer sur un émulateur ou un appareil physique avec ▶ **Run 'app'**.

En ligne de commande :

```bash
./gradlew assembleDebug    # génère app/build/outputs/apk/debug/app-debug.apk
./gradlew installDebug     # installe sur l'appareil connecté
```
