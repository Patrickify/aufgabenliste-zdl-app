# aufgabenliste-zdl-app
import 'package:flutter/material.dart';

void main() {
  runApp(AufgabenApp());
}

class AufgabenApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Aufgabenliste ZDL',
      theme: ThemeData(primarySwatch: Colors.blue),
      home: AufgabenHome(),
    );
  }
}

class AufgabenHome extends StatefulWidget {
  @override
  _AufgabenHomeState createState() => _AufgabenHomeState();
}

class _AufgabenHomeState extends State<AufgabenHome> {
  String username = '';
  bool loggedIn = false;

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Aufgabenliste ZDL')),
      body: Padding(
        padding: EdgeInsets.all(16),
        child: loggedIn ? Center(child: Text('Hallo, $username')) : buildLogin(),
      ),
    );
  }

  Widget buildLogin() {
    TextEditingController ctrl = TextEditingController();
    return Column(
      mainAxisAlignment: MainAxisAlignment.center,
      children: [
        Text('Bitte Namen eingeben:'),
        TextField(controller: ctrl),
        SizedBox(height: 12),
        ElevatedButton(
          child: Text('Los geht’s'),
          onPressed: () {
            if (ctrl.text.trim().isNotEmpty) {
              setState(() {
                username = ctrl.text.trim();
                loggedIn = true;
              });
            }
          },
        ),
      ],
    );
  }
}
name: aufgabenliste_zdl_app
description: Starter für Aufgaben-App ZDL
publish_to: 'none'

version: 0.1.0
environment:
  sdk: ">=2.17.0 <3.0.0"

dependencies:
  flutter:
    sdk: flutter

dev_dependencies:
  flutter_test:
    sdk: flutter

flutter:
  uses-material-design: true
# Aufgabenliste ZDL 🌟

Starterprojekt für deine Aufgaben-App.

## 🚀 Erste Schritte

1. Repository klonen oder importieren nach Replit.
2. Replit klicken auf „Run“.
3. App im Browser starten.
4. Namen eingeben und Hello-Screen testen.

## 🧩 Nächste Schritte

- Aufgabenliste via Google Sheet abrufen
- Anzeige der täglichen Aufgaben
- Abhaken mit Zeiten und Namen
- Push-Erinnerungen einbauen

## ℹ️ Hinweis

Arbeitet komplett im Browser mit Replit + GitHub – keine lokale Installation nötig.
