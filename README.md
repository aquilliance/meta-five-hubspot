# HubSpot-Formular Integration in WordPress

Diese Anleitung erklärt, wie das HubSpot-Formular samt eigenem CSS in Ihre WordPress-Seite integriert wird.

---

## 1. Voraussetzungen

- Zugriff auf das WordPress-Backend (Seiten-/Beitragseditor)
- Das mitgelieferte CSS (siehe unten)
- Das Formular stammt aus HubSpot (portalId & formId sind im Beispiel hinterlegt)

---

## 2. Formular einbinden

1. Öffnen Sie im WordPress-Backend die Seite oder den Beitrag, auf der/dem das Formular erscheinen soll.
2. **Fügen Sie einen "Individuellen HTML-Block"** (Custom HTML) an der gewünschten Stelle ein.
3. Kopieren Sie folgenden Code dort hinein:

    ```html
    <div class="form-outer">
      <div class="form-inner">
        <script
          charset="utf-8"
          type="text/javascript"
          src="//js-eu1.hsforms.net/forms/embed/v2.js"
        ></script>
        <script>
          hbspt.forms.create({
            portalId: "143242019",
            formId: "e649fb1f-be5a-4b04-9d64-0782259a6d43",
            region: "eu1"
          });
        </script>
      </div>
    </div>
    ```

> **Hinweis:**  
> WordPress kann in einigen Fällen das direkte Einfügen von Skripten im Editor verhindern oder filtern.  
> Sollte das Script entfernt werden, verwenden Sie ein Plugin wie  
> [WPCode – Insert Headers and Footers](https://de.wordpress.org/plugins/insert-headers-and-footers/)  
> oder [Code Snippets](https://de.wordpress.org/plugins/code-snippets/).

---

## 3. CSS-Styles einfügen

**Option A: WordPress Customizer**

1. Gehen Sie auf  
   `Design → Customizer → Zusätzliches CSS`
2. Fügen Sie das bereitgestellte CSS (siehe unten) dort vollständig ein.
3. Änderungen speichern.

**Option B: Im (Child-)Theme**

- Öffnen Sie die Datei `style.css` Ihres (Child-)Themes.
- Fügen Sie das CSS am Ende ein und speichern Sie die Datei.

---

## 4. Schriftart "Open Sans" einbinden

Damit das Formular wie vorgesehen aussieht, sollte die Schriftart "Open Sans" geladen werden.  
Falls Ihr Theme diese nicht lädt, fügen Sie folgendes in den `<head>`-Bereich der Seite ein (z.B. über den Customizer → Zusätzliches CSS/JS oder ein Snippet-Plugin):

```html
<link href="https://fonts.googleapis.com/css?family=Open+Sans:400,500,700&display=swap" rel="stylesheet">
