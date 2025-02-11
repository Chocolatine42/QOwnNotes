# Exponierte Klassen

Notiz
----

### Eigenschaften und Methoden
```cpp
class NoteApi {
    Q_PROPERTY(int id)
    Q_PROPERTY(QString name)
    Q_PROPERTY(QString fileName)
    Q_PROPERTY(QString fullNoteFilePath)
    Q_PROPERTY(QString fullNoteFileDirPath)
    Q_PROPERTY(QString relativeNoteFileDirPath)
    Q_PROPERTY(int noteSubFolderId)
    Q_PROPERTY(QString noteText)
    Q_PROPERTY(QString decryptedNoteText)
    Q_PROPERTY(bool hasDirtyData)
    Q_PROPERTY(QQmlListProperty<TagApi> tags)
    Q_PROPERTY(QDateTime fileCreated)
    Q_PROPERTY(QDateTime fileLastModified)
    Q_INVOKABLE QStringList tagNames()
    Q_INVOKABLE bool addTag(QString tagName)
    Q_INVOKABLE bool removeTag(QString tagName)
    Q_INVOKABLE bool renameNoteFile(QString newName)
    Q_INVOKABLE QString toMarkdownHtml(bool forExport = true)
    Q_INVOKABLE QString getFileURLFromFileName(QString localFileName)
    Q_INVOKABLE bool allowDifferentFileName()
};
```

Sie können die Methoden von [Datum](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) verwenden, um mit `fileCreated` oder `fileLastModified` zu arbeiten.

### Beispiel
```js
script.log (note.fileCreated.toISOString ());
script.log (note.fileLastModified.getFullYear ());

// benennt eine Notiz in "new name.md" um
note.renameNoteFile ("neuer Name");

// prüfe ob es einen anderen Namen der Notendatei als die Überschrift haben darf
script.log (note.allowDifferentFileName ());
```

NoteSubFolder
----

### Eigenschaften und Methoden
```cpp
class NoteSubFolderApi {
    Q_PROPERTY(int id)
    Q_PROPERTY(QString name)
    Q_PROPERTY(QQmlListProperty<NoteApi> notes)
    Q_INVOKABLE static NoteSubFolderApi *fetchNoteSubFolderById(int id);
    Q_INVOKABLE static QList<QObject*> fetchNoteSubFoldersByParentId(int parentId);
};
```

### Beispiel
```js
script.log (noteSubFolder.id);
script.log (noteSubFolder.name);

// Notizen im Unterordner durchlaufen
für (var idx in noteSubFolder.notes) {
     var note = noteSubFolder.notes [idx];
}}

// Alle Unterordnernamen drucken
noteSubFolder.fetchNoteSubFoldersByParentId (parentId).forEach (function (nsf) {
     script.log (nsf.name);
});
```

Schlagwort
---

### Eigenschaften und Methoden
```cpp
class TagApi {
    Q_PROPERTY(int id)
    Q_PROPERTY(QString name)
    Q_PROPERTY(int parentId)
    Q_INVOKABLE TagApi fetchByName(const QString &name, int parentId = 0)
    Q_INVOKABLE QStringList getParentTagNames()
};
```

HauptFenster
----------

### Eigenschaften und Methoden
```cpp
class MainWindow {
    Q_INVOKABLE void reloadTagTree();
    Q_INVOKABLE void reloadNoteSubFolderTree();
    Q_INVOKABLE void buildNotesIndexAndLoadNoteDirectoryList(
            bool forceBuild = false, bool forceLoad = false);
    Q_INVOKABLE void focusNoteTextEdit();
    // Creates a new note subfolder in the current subfolder
    Q_INVOKABLE bool createNewNoteSubFolder(QString folderName = "");
    // Inserts html in the current note as markdown
    // This method also downloads remote images and transforms "data:image"
    // urls to local images stored in the media directory
    Q_INVOKABLE void insertHtmlAsMarkdownIntoCurrentNote(QString html);
    // Reloads the current note by id
    // This is useful when the path or filename of the current note changed
    Q_INVOKABLE void reloadCurrentNoteByNoteId();
    // Returns the list of workspace UUIDs
    Q_INVOKABLE QStringList getWorkspaceUuidList();
    // Returns the UUID of a workspace, passing in the workspace name
    Q_INVOKABLE QString getWorkspaceUuid(const QString &workspaceName);
    // Sets the current workspace by UUID
    Q_INVOKABLE void setCurrentWorkspace(const QString &uuid);
};
```

### Beispiel
```js
// Erzwingt ein Neuladen der Notizliste
mainWindow.buildNotesIndexAndLoadNoteDirectoryList(true, true);

// Erstellt einen neuen Notiz-Unterordner "Mein schicker Ordner" im aktuellen Unterordner
mainWindow.createNewNoteSubFolder("My fancy folder");

// Fügt HTML als Markdown in die aktuelle Notiz ein
mainWindow.insertHtmlAsMarkdownIntoCurrentNote("<h2>my headline</h2>some text");

// Legt Arbeitsbereich 'Bearbeiten' als aktuellen Arbeitsbereich fest
mainWindow.setCurrentWorkspace(mainWindow.getWorkspaceUuid("Edit"));




mainWindow.buildNotesIndexAndLoadNoteDirectoryList(true, true);

// Erstellt einen neuen Notiz-Unterordner "Mein schicker Ordner" im aktuellen Unterordner
mainWindow.createNewNoteSubFolder("Mein ausgefallener Ordner");

// Fügt HTML als Markdown in die aktuelle Notiz ein
mainWindow.insertHtmlAsMarkdownIntoCurrentNote("<0>meine Überschrift</0>etwas Text");


mainWindow.setCurrentWorkspace(mainWindow.getWorkspaceUuid("Bearbeiten"));
```
