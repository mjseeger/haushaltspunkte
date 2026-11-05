# Haushaltspunkte

Eine kleine Web-App (PWA) für zwei Personen, die sich den Haushalt teilen. Jede erledigte Aufgabe bringt Punkte – so sieht man auf einen Blick, wer wie viel gemacht hat.

## Funktionen

- **Aufgaben mit Punktwerten** – einmalig, täglich oder wöchentlich wiederkehrend
- **Wischen zum Abhaken** – nach rechts: Punkte für mich, nach links: Punkte für den Partner / die Partnerin
- **Punktestand** für beide Personen
- **Gemeinsame Einkaufsliste** als zweiter Tab (hinzufügen, abhaken, löschen)
- **Login per E-Mail/Passwort**, Zugriff auf genau zwei freigegebene Adressen beschränkt
- **Installierbar** auf iPhone und Android („Zum Home-Bildschirm“), Echtzeit-Sync zwischen beiden Handys

## Technik

- Reines HTML/CSS/JavaScript in einer Datei (`public/index.html`), kein Build-Schritt
- [Firebase](https://firebase.google.com/) Authentication, Cloud Firestore (Region Frankfurt) und Hosting – läuft komplett im kostenlosen Spark-Tarif
- Firestore-Sicherheitsregeln in `firestore.rules`

## Selbst betreiben

1. Firebase-Projekt anlegen, E-Mail/Passwort-Login und Firestore aktivieren
2. Eigene Web-App-Konfiguration in `public/config.js` eintragen, Projekt-ID in `.firebaserc`
3. In `firestore.rules` die beiden erlaubten E-Mail-Adressen eintragen (im Repo stehen Platzhalter)
4. Deployen:

   ```bash
   npm install -g firebase-tools
   firebase login
   firebase deploy
   ```

Eine ausführlichere Schritt-für-Schritt-Anleitung steht in [`ANLEITUNG.txt`](ANLEITUNG.txt).

> Hinweis: Die Werte in `config.js` sind die öffentliche Firebase-Web-Konfiguration; der Schutz der Daten erfolgt über die Sicherheitsregeln.
