# Raider Retro C

A retro theme for Home Assistant with light and dark modes. The light mode looks like cream paper. The dark mode is night blue-grey with four colour stripes and a slight CRT effect.

![Preview](images/preview.png)

## Features

- **Light and dark mode.** The theme follows the dark/light setting in your Home Assistant profile.
- **Random stripe on every card.** Each card gets a red, yellow, green and turquoise top stripe in a random order and with random widths. It is redrawn on every page load.
- **CRT effect.** Cards have scanlines and grain, and from time to time a short burst of interference. Each card bursts at a different moment.
- **Pulsing background.** In dark mode the background stripes flash now and then. The animation is built into the theme, so there are no extra files to copy.
- **Quieter media players.** A player without artwork gets a soft tint instead of a solid colour block. Players that are off or unavailable become see-through and dimmed.
- **Reduced motion.** All animations stop when your system asks for reduced motion.

## Requirements

- [HACS](https://hacs.xyz)
- [card-mod](https://github.com/thomasloven/lovelace-card-mod), which draws the stripes, CRT effect and media player styling. Without it you still get the colours and font, but the cards are plain.

## Installation

### HACS

1. Go to **HACS → ⋮ → Custom repositories**, enter `https://github.com/Prznitel/hacs-raider-retro` and pick the **Theme** category.
2. Search for **Raider Retro C** and install it.
3. Make sure `configuration.yaml` loads themes:

   ```yaml
   frontend:
     themes: !include_dir_merge_named themes
   ```

4. Restart Home Assistant, or run the `frontend.reload_themes` action.

### Manual

Copy `themes/raider-retro-c.yaml` to `/config/themes/`, then do steps 3 and 4 above.

## Font

The theme uses **Barlow Condensed**. Add it as a dashboard resource:

1. Open **Settings → Dashboards → ⋮ → Resources → Add resource**.
2. URL: `https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@400;500;600;700&display=swap`
3. Resource type: **Stylesheet**

## Using the theme

- **Whole interface:** Profile → Theme → `Raider Retro C`
- **One dashboard:** edit each view and set its theme to `Raider Retro C`

## Customization

Each mode has two variables near the top that you can change:

| Variable | Meaning | Light | Dark |
|---|---|---|---|
| `rr-crt` | CRT effect strength (0 = off, 1 = full) | `0.35` | `1` |
| `rr-static-period` | How often interference appears (longer = less often) | `14s` | `9s` |

You can also put your own picture under the stripes. Upload it to `/config/www/`, then add `url('/local/your-image.jpg') center / cover no-repeat fixed` to `lovelace-background` in the dark mode.

## Made with AI

This theme was created with the help of [Claude](https://claude.ai), an AI assistant by Anthropic.

## License

[MIT](LICENSE)

---

## Česky

Retro motiv pro Home Assistant se světlým a tmavým režimem. Každá karta má nahoře barevný pruh v náhodném pořadí a s náhodnými šířkami. Tmavý režim má navíc jemný CRT efekt a občas zapulzuje pozadí.

Potřebuje [card-mod](https://github.com/thomasloven/lovelace-card-mod) a písmo Barlow Condensed přidané jako zdroj dashboardů (postup je v části **Font** výše). Instalace přes HACS: **Vlastní repozitáře → kategorie Motiv**.

Motiv vznikl s pomocí AI asistenta [Claude](https://claude.ai) od společnosti Anthropic.
