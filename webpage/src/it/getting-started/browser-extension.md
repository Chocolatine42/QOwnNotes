---
image: /img/bookmarks.png
---

# Estensione del browser QOwnNotes Web Companion

Allows for clipping from a browser page and managing browser bookmarks across browsers and operating systems.

::: tip
Info
- QOwnNotes must be running for the Web Companion browser extension to work.
- No internet connection needed. The browser extensions works **offline**.
:::

## Installation

1. Get the extension
    - [Chrome Web Store](https://chrome.google.com/webstore/detail/qownnotes-web-companion/pkgkfnampapjbopomdpnkckbjdnpkbkp)
    - [Firefox Add-ons page](https://addons.mozilla.org/firefox/addon/qownnotes-web-companion)
    - You can also find the extension on [GitHub](https://github.com/qownnotes/web-companion/).
2. Add the Security Token to configure the extension.
    - The first time you click on the QOwnNotes browser extension icon you will receive a dialog box with a security token. Copy the token.
    - Go to your browser's extension management location. Click into the QOwnNotes extension details.
    - Paste the token into the Security Token field.

## Web clipper

![web-clipper](/img/web-clipper.png)

Right-click on a webpage or selected text to use the **web-clipper** functionality. There you can also create a new note with a **screenshot** of the current webpage.

::: tip
The web clipper is also scriptable! Take a look at the [websocketRawDataHook](../scripting/hooks.md#websocketrawdatahook) if you want to control what you clip from webpages.
:::

## Bookmarks

![bookmarks](/img/bookmarks.png)

If you want full control over your browser bookmarks and **use them across different browsers and operating systems** then the QOwnNotes browser extension is for you.

By default the browser extension will show all **links of the current note** in a popup when you click the QOwnNotes icon in your browser. These links will get a tag `current`.

You can also **manage your bookmarks in notes** with the note tag `bookmarks` (changeable in the settings). These links can also have tags and a description that will be shown in the browser extension.

New bookmarks are stored in a note called `Bookmarks` (also changeable in the settings).

::: tip
You can also import your browser bookmarks into QOwnNotes with the web companion browser extension!
:::

### Sintassi dei collegamenti segnalibri

```markdown
- [Nome pagina web](https://www.example.com)
- [Nome pagina web](https://www.example.com) #etichetta1 #etichetta2
- [Nome pagina web](https://www.example.com) solo descrizione
- [Nome pagina web](https://www.example.com) #etichetta1 #etichetta2 descrizione e etichette
* [Nome pagina web](https://www.example.com) funziona anche il carattere lista alternativo
```

You are able to search for name, url tags or description in the browser extension.
