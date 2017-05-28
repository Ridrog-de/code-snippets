---
title: VUE Components mit Menü
published: true
date: '27-05-2017 16:52'
publish_date: '27-05-2017 16:52'
taxonomy:
    language:
        - js
    framework:
        - vuejs
menu: Components mit Menü
slug: components-menu
---

### 1. HTML Markup
Zuerst eine Komponente für das Menü.  
Dann mehrere Komponenten, für die verschiedenenen Bereiche.
Natürlich mit Animation beim wechseln.

```html
<admin-menu></admin-menu>

<component :is="currentView" transition="expand" transition-mode="out-in"></component>
```

### 2. Die Animation

```css
.expand-transition {
  transition: all .8s ease;
  max-height: 2600px;
  overflow: hidden !important;
}

.expand-enter, .expand-leave {
  max-height: 0;

}
```

### 3. Javscript

Um die Vue Instanz zu erstellen hat man nun verschiedene Möglichkeiten.

1. Eine Haupt JS Datei erstellen
	2. alles einbinden (vue + komponenten)
	3. Die vue instanz erstellen
2. Eine Funktion erstellen
	3. Vue wird über eine andere Datei dem window zugänglich gemacht (optional).
	4. Einbinden der Komponenten
	6. In der Seite wird dann die Funktion aufgerufen die die Vue Instanz erstellt, und es werden Daten übergeben.
3. Nur die Komponenten erstellen
	4. Es existiert eine Master Vue Instanz
	5. Die Komponenten werden global verfügbar gemacht 


### WIP

- Vue wird in meiner Haupt JS Datei eingebunden und dem Window zugänglich gemacht.
- Ich erstelle alle Komponenten 
- Binde diese ein und generiere eine Vue Instanz
