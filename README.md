# Abonnemangskoll

En liten installerbar webbapp (PWA) för att hålla koll på alla dina
prenumerationer: total kostnad per månad och år, kategorifördelning och
vad som förnyas eller vilken gratis provperiod som snart tar slut.

- **Fristående app** – installeras på hemskärmen (Android/iOS) och körs i
  helskärm utan webbläsar-ram.
- **Fungerar offline** – via en service worker.
- **Lokal data** – dina abonnemang sparas bara i webbläsarens lagring på
  din egen enhet. Inget skickas till någon server.

## Köra lokalt

```bash
python3 -m http.server 8137
# öppna http://localhost:8137
```

Service workern (offline + installation) kräver `https://` eller
`http://localhost`.

## Publicerad

Hostad via GitHub Pages. Öppna sidan i Chrome på Android och välj
**⋮ → Installera app** för att lägga den på hemskärmen.

## Innehåll

| Fil | Roll |
| --- | --- |
| `index.html` | Hela appen (UI + logik) |
| `manifest.webmanifest` | App-metadata för installation |
| `sw.js` | Service worker för offline |
| `icons/` | App-ikoner (vanliga + maskable) |

## Påminnelser

Appen kan inte skicka push-notiser av sig själv. Istället visar vyn
**På gång** vad som förnyas de närmaste 31 dagarna, och varje rad har en
**Lägg i kalender**-länk som skapar en händelse i Google Kalender.
