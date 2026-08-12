---
title: Alltagshelfer – Datenschutzerklärung
layout: page
permalink: /dailyflow/privacy/de/
---

# Alltagshelfer – Datenschutzerklärung

**Sprachen:** [English](/dailyflow/privacy/) · Deutsch · [Español](/dailyflow/privacy/es/) · [Português (BR)](/dailyflow/privacy/pt-br/)

**App:** Alltagshelfer / DailyFlow (`com.marvelsofcode.dailyflow`)
**Stand:** 12. August 2026

## 1. Verantwortlicher

Tobias Wilker
E-Mail: [tobias.wilker@gmail.com](mailto:tobias.wilker@gmail.com)

Verantwortlicher im Sinne der DSGVO für die hier beschriebenen Verarbeitungen. Bei Fragen zu dieser Erklärung oder zu deinen Daten schreib mir an die obige Adresse.

## 2. Kurzfassung

Alltagshelfer ist eine „local first“-App. Deine Aufgaben, wiederkehrenden Aufgaben, Routinen, Checklisten, Statistiken, der Verlauf und deine Einstellungen liegen **ausschließlich auf deinem Gerät**. Es gibt kein Konto, keine Anmeldung und kein Nutzerprofil auf einem Server von mir. Ich erhebe, empfange, verkaufe und teile keine personenbezogenen Daten von dir.

Die App enthält **keine Werbung, kein Tracking und keine Analyse**. Das Firebase-Analytics-SDK wurde bewusst entfernt.

Zwei optionale Funktionen senden Daten vom Gerät, und zwar nur, wenn du sie nutzt: **Gruppen-Teilen / Delegieren** und **Google-Drive-Sicherung**. Beide werden unten beschrieben.

## 3. Daten auf deinem Gerät

Lokal gespeichert werden: Aufgaben und Termine, Wiederholungsregeln, Routinen, Checklisten samt Einträgen, der Verlauf erledigter Aufgaben, Statistiken, Profile, Gruppenzugehörigkeit samt kryptografischen Schlüsseln sowie deine Einstellungen. Diese Daten verlassen dein Gerät nur über die beiden optionalen Funktionen in den Abschnitten 4 und 5.

Der Verlauf erledigter Aufgaben wird automatisch gemäß der von dir eingestellten Aufbewahrungsdauer gelöscht.

Durch Deinstallation der App werden all diese Daten gelöscht.

## 4. Gruppen-Teilen und Delegieren (optional)

Wenn du über den QR-Code eines anderen Geräts einer Gruppe beitrittst, kannst du Aufgaben, Routinen und Checklisten mit den anderen Mitgliedern teilen und Aufgaben an sie delegieren.

- **Ende-zu-Ende-Verschlüsselung.** Alles, was dein Gerät für ein anderes Mitglied verlässt, wird auf deinem Gerät mit AES-256-GCM verschlüsselt (pro Nachricht ein neuer Zufalls-IV, 128-Bit-Authentifizierungs-Tag).
- **Der Schlüssel erreicht keinen Server.** Der 256-Bit-Gruppenschlüssel wird auf deinem Gerät erzeugt und ausschließlich im QR-Code übertragen, den du der anderen Person zeigst. Er wird nie hochgeladen, und ich besitze ihn nicht.
- **Was der Transportweg sieht.** Verschlüsselte Nachrichten werden über eine Google-Cloud-Function von mir (Firebase-Projekt `dailyflow-502909`) weitergeleitet und per Firebase Cloud Messaging zugestellt. Der Relay sieht nur das Messaging-Token des Empfängers, den undurchsichtigen Chiffretext, einen Collapse-Key und eine Absender-Gerätekennung. Er kann den Inhalt nicht lesen, und der Inhalt wird in keiner Datenbank von mir gespeichert.
- **Speicherdauer.** Nicht sofort zustellbare Nachrichten hält Firebase Cloud Messaging höchstens für die maximale Lebensdauer von vier Wochen vor und verwirft sie dann. Die zugehörige lokale Sendewarteschlange auf deinem Gerät wird im gleichen Rhythmus geleert.
- **Missbrauchsschutz.** Firebase App Check (Play Integrity) schützt den Relay-Endpunkt vor Missbrauch durch fremde Clients.
- **Auftragsverarbeiter.** Google Ireland Limited / Google LLC für Firebase Cloud Messaging und Cloud Functions. Datenschutzhinweise von Google: <https://firebase.google.com/support/privacy>.
- **Rechtsgrundlage.** Art. 6 Abs. 1 lit. b DSGVO — Verarbeitung zur Erbringung der von dir angeforderten Teilen-Funktion. Trittst du keiner Gruppe bei, werden keine Daten übertragen.

Beachte: Die anderen Gruppenmitglieder können die von dir geteilten Inhalte naturgemäß sehen. Teile nur mit Personen, denen du vertraust.

## 5. Google-Drive-Sicherung (optional)

Startest du eine Sicherung, fragt die App die Berechtigung für genau einen Google-Drive-Bereich an: `https://www.googleapis.com/auth/drive.appdata`. Dieser Bereich gewährt Zugriff **ausschließlich auf den eigenen versteckten App-Datenordner** in deinem Drive. Die App kann deine übrigen Google-Drive-Dateien nie sehen, lesen oder ändern, und sie fragt weder Name noch E-Mail-Adresse oder Profil ab.

Das Sicherungsarchiv enthält deine lokale Datenbank, deine Einstellungen und einen Abzug deiner Gruppenkonfiguration. Es liegt **in deinem eigenen Google-Drive-Konto**, unter deiner Kontrolle, und ist durch Googles Verschlüsselung im Ruhezustand geschützt. Eine zusätzliche Verschlüsselung durch die App erfolgt nicht. Ich habe keinen Zugriff auf dein Drive oder die Sicherungsdatei. Du kannst sie jederzeit im App-Datenspeicher deines Google-Kontos löschen und die Berechtigung unter <https://myaccount.google.com/permissions> widerrufen.

**Rechtsgrundlage.** Art. 6 Abs. 1 lit. a/b DSGVO — du stößt die Sicherung ausdrücklich selbst an.

## 6. Berechtigungen und wofür sie gebraucht werden

| Berechtigung | Zweck |
| --- | --- |
| Benachrichtigungen | Wecker für fällige Aufgaben und die optionale Tageszusammenfassung |
| Exakte Alarme | Klingeln genau zur eingestellten Zeit — ein ungenauer Erinnerungswecker wäre nutzlos |
| Vollbild-Intent | Anzeigen und Beenden des Weckers auf dem Sperrbildschirm |
| Vordergrunddienst (Medienwiedergabe) | Weiterspielen des Wecktons, während der Wecker klingelt |
| Beim Start ausführen | Erneutes Einplanen offener Wecker nach einem Neustart des Geräts |
| Internet / Netzwerkstatus | Nur für den verschlüsselten Relay (Abschnitt 4) und die Drive-Sicherung (Abschnitt 5) |
| Kamera | Scannen des Gruppen-QR-Codes. Es werden keine Fotos oder Videos gespeichert oder übertragen |

## 7. Kinder

Alltagshelfer ist eine Produktivitäts-App für ein allgemeines Publikum. Sie richtet sich nicht an Kinder und erhebt wissentlich keine Daten von ihnen.

## 8. Deine Rechte

Nach der DSGVO hast du das Recht auf Auskunft, Berichtigung, Löschung, Einschränkung der Verarbeitung, Datenübertragbarkeit und Widerspruch sowie das Recht auf Beschwerde bei einer Aufsichtsbehörde.

Da ich keine personenbezogenen Daten über dich vorhalte, gibt es praktisch nichts, was ich herausgeben oder löschen könnte. Du übst diese Rechte direkt aus: Deinstalliere die App, um alle lokalen Daten zu löschen, lösche deine Drive-Sicherung und widerrufe die Drive-Berechtigung in deinem Google-Konto, und verlasse Gruppen, denen du beigetreten bist. Bei Fragen erreichst du mich unter [tobias.wilker@gmail.com](mailto:tobias.wilker@gmail.com).

## 9. Änderungen dieser Erklärung

Änderungen werden auf dieser Seite mit neuem Stand veröffentlicht. Wesentliche Änderungen werden zusätzlich in den Versionshinweisen der App genannt.
