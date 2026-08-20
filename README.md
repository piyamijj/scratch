# 🎰 Scratch Card — Kazı Kazan

Interactive **scratch card** web page: a cloud-texture overlay hides a secret image, and the user scratches (swipes with finger or mouse) to reveal what's underneath.

**🔗 Live demo:** https://static.teamily.ai/sites/e1097d88-d032-4351-9aca-f8f21e1e9dcc/webpages/scratch-card/index.html

## ✨ Features

- ☁️ **Cloud overlay** — AI-generated tiling cloud texture fully covers the card
- 🖐️ **Canvas scratch effect** — real erasing via `destination-out`; works with touch (mobile) and mouse (desktop) through Pointer Events
- 🎯 **Auto-reveal** — card opens automatically once **42%** of the surface is scratched
- 🎉 **"Voilà!" sound** — plays the moment the card is revealed (French TTS), re-armed on every reset
- 🔁 **Reset buttons** — "Tekrar Kazı" (scratch again) and "Bulutları Geri Getir" (restore clouds)
- 📱 **Mobile-first** — clean dark design, works on any device

## 🚀 How to Run

No build step, no dependencies — open the page in any modern browser:

```bash
# Option 1: just open the file
open index.html

# Option 2: serve locally
python3 -m http.server 8000
# then visit http://localhost:8000
```

## 📁 Files

| File | Purpose |
|------|---------|
| `index.html` | The whole app (HTML + CSS + JS) |
| `images/cloud_texture.png` | Cloud overlay texture |
| `images/secret.jpg` | Hidden image revealed by scratching |
| `images/voila.mp3` | "Voilà!" reveal sound effect |

## 🛠️ How It Works

1. `index.html` draws the secret image as the base layer.
2. A `<canvas>` on top is painted with the cloud texture in a repeating pattern.
3. Pointer/mouse movement erases the canvas (`globalCompositeOperation = 'destination-out'`), revealing the image below.
4. When the erased area reaches 42% of the card, the card animates open and the "Voilà!" sound plays (audio is unlocked on the first touch/click to satisfy browser autoplay policies).

---

Built with ❤️ — scratch away and enjoy! 🎭
