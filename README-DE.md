## Ich brauche eine gute Sass-Projektstruktur. kannst du mir helfen?

## So 1 2 3 und los

- [Struktur](#Struktur)
- [Importieren](#Importieren)
- [Dateideklaration](#Dateideklaration)
- [Setup](#setup)

## Struktur

Weil es vielen von euch schwer fällt, die neue Struktur von sass zu strukturieren oder umzusetzten, teile dieses Dokument mit euch. Dies ist das allgemeine Setup, dass du möglicherweise für deinen Build benötigst. Natürlich können sich die Dinge manchmal ändern, aber dies ist ein Überblick darüber, was du haben kannst.

```
scss/
|
|- abstracts/
|	|- __abstracts-dir.scss     # Alle Abstracts .scss Dateien importieren
|	|- _fonts.scss              # Schriftimport
|	|- _mixins.scss             # Scss Mixins
|	|- _variables.scss          # Scss Variablen
|	|- _functions.scss          # Scss Funktionen (falls gibt)
|
|- base/
|	|- __base-dir.scss          # Alle .scss Basisdateien importieren
|	|- _reset.scss              # Benutzerdefiniertes
|	|- _typography.scss         # Typografieregeln
|	…                           # Rest falls du hast..
|
|- components/
|	|- __components-dir.scss    # Alle .scss Dateien der Komponenten importieren
|	|- _button.scss             # Schaltflächenstile
|	|- _input.scss              # Eingabestile
|	|- _modal.scss              # Modale Stile
|	…	                         # Rest falls du hast..
|
|- layouts/
|	|- __layouts-dir.scss       # Alle Layouts .scss Dateien importieren
|	|- _footer.scss             # Footer stile
|	|- _main-menu.scss          # Hauptnavigationsstile
|	…                           # Rest falls du hast..
|
|- vendor/
|	|- __vendor-dir.scss        # Import vendor folders (All of the out side tools that you need for your project)
|	|- fontawesome/             # Font Awesome
|	|- normalize/               # Normalisieren
|	…                           # Rest falls du hast..
|
main.scss                       # Haupt-Scss-Datei
```

## Importieren

in `main.scss` musst du alle Dateien importieren, die mit `-dir.scss` enden
Denk daran, dass alle Dateinamen neben deiner `main.scss` mit `_` beginnen sollten
Auch deine Anbieter und Abstracts sollten die ersten sein, die du importierst

```
//Vendor
@import "vendor/__vendor-dir";

//Abstracts
@import "abstracts/__abstracts-dir";

//Base Styles
@import "base/__base-dir";

//Components
@import "components/__components-dir";

//Layout
@import "layouts/__layouts-dir";

```

## Dateideklaration

## `Vendors`

Hier fügst du alle Tools von Drittanbietern hinzu, z. B. Fontawesome, Normalize und alle anderen.

## `Abstracts`

Alle Variablen, die du Mixins oder Funktionen hast, kannst du hier hinzufügen, so dass es eine Art Ihrer eigenen Setups für dein Projekt ist.

## `Base`

Du kannst dein Anpassungen für dein Basis festlegen, dein eigene Normalisierung oder allgemeine Regeln für Schlagzeilen festlegen.

## `Components`

Geh tief in deine Elemente ein, was deine Webseite definiert, welche Komponenten, auf die du dich verlassen, Beispiel (Formulare, Registrierungsformulare, Galerie, ...)
Tipp: du würdest hier die tatsächliche Verwendung sehen, wenn wir anfangen, mit React zu arbeiten

## `layout`

Definierst du dein Layout, wie diene Webseite aussieht

## Setup

1. Klon dieses Repository in einen neuen Projektordner ( ersetzt `[Projektname]` durch den Namen deines Projekts)

   ```
   git clone git@github.com:hnsreeny/sass-structure-template.git [project name]
   ```

1. Lösch den Git-Verlauf der Boilerplate, um sicherzustellen, dass der Projektverlauf nur deine Commits enthält

   ```
   cd <project name>
   rm -rf .git
   ```

1. Bearbeitet `package.json`, um den Namen deines Projekts hinzuzufügen

   `package.json`

   ```json
   {
     "name": "[Projektname]",
     ...
     "author": "[dein name]"
   }
   ```

1. Bearbeitet `src/index.html`, um den Namen deines Projekts hinzuzufügen

   ```html
   ...
   <head>
     ...
     <title>[Projektname]</title>
   </head>
   ...
   ```

1. Start ein neues Git-Repository und führst du einen anfänglichen Commit durch. Dadurch wird sichergestellt, dass du mit Git an deinem Projekt arbeiten kannst.

   ```
   git init
   git add . && git commit -m "Initial commit"
   ```

1. Installierst du die Abhängigkeiten

```
npm install
```

1. Happy coding ☘️

