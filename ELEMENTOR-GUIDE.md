# Sådan indsætter du 3D Workshop i WordPress med Elementor

## Metode 1: Dedikeret side med Custom HTML (Anbefalet)

### Trin 1: Upload filen
1. Upload `index.html` til din WordPress-server via FTP/SFTP til fx:
   ```
   /wp-content/uploads/3d-workshop/index.html
   ```

### Trin 2: Opret en ny side i WordPress
1. Gå til **Sider → Tilføj ny** i WordPress
2. Giv siden en titel, fx "3D Workshop"
3. Klik **Rediger med Elementor**

### Trin 3: Opsæt Elementor-layoutet
1. Klik på **tandhjulet** (nederst til venstre) → **Sideindstillinger**
2. Sæt **Sidelayout** til **Elementor Full Width** (eller **Elementor Canvas** for helt uden header/footer)
3. Tilføj en **Sektion** og sæt den til fuld bredde:
   - Klik på sektionen → **Layout** → Content Width: **Full Width**
   - **Avanceret** → sæt alle margins og padding til **0**

### Trin 4: Indsæt iFrame
1. Træk en **HTML** widget ind i sektionen
2. Indsæt følgende kode:

```html
<div style="width:100%;height:100vh;overflow:hidden;">
  <iframe
    src="/wp-content/uploads/3d-workshop/index.html"
    style="width:100%;height:100%;border:none;"
    allowfullscreen>
  </iframe>
</div>
```

3. Klik **Opdater/Publicer**

---

## Metode 2: Inline HTML (uden upload)

Hvis du foretrækker at indsætte alt direkte:

1. Opret en ny side med **Elementor Canvas** layout
2. Tilføj en **HTML** widget
3. Kopiér hele indholdet af `index.html` og indsæt det i HTML-widgetten
4. **Bemærk:** Elementor kan have problemer med meget store HTML-blokke

---

## Metode 3: Via tema-fil (avanceret)

1. Opret en custom page template i dit Astra child theme
2. Kopiér indholdet af `index.html` ind i template-filen
3. Tildel templaten til din nye side

---

## Tips

- **Canvas layout** giver den bedste oplevelse da header/footer fjernes
- Sørg for at Three.js CDN-linket er tilgængeligt (det bruger cdnjs.cloudflare.com)
- Test på mobil – first-person controls virker bedst på desktop
- Siden bruger Pointer Lock API som kræver brugerinteraktion for at aktivere
