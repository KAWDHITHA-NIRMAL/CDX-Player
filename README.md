# CDX Plyer (by K.Nirmal)
High-performance Lottie & TGS (.cdx) player for the web. No dependencies needed in your HTML, it auto-loads Lottie from CDN.

[![Status](https://img.shields.io/badge/Status-Active-brightgreen.svg?style=for-the-badge&logo=github)]()
[![Type](https://img.shields.io/badge/Type-Web_Component-blue.svg?style=for-the-badge&logo=javascript)]()
[![License](https://img.shields.io/badge/License-MIT-orange.svg?style=for-the-badge)]()

---

🚀 Features
- **Auto Decompression:** Directly plays .cdx, .tgs, and GZipped Lottie files.
- **Smart Caching:** Uses Browser Cache API to save bandwidth.
- **Ultra Lightweight:** Single file, easy to integrate.
- **Framework Ready:** Works in React, Vue, Angular, and Plain HTML.
- **Zero-Config:** Automatically injects its own dependencies (Bodymovin/Lottie).

---

📦 Installation (NPM)
```bash
npm install cdx-plyer
```

**Example package.json**
If you are building a React/Next.js or Node project, your `package.json` should look like this:

```json
{
  "name": "my-animation-project",
  "version": "1.0.2",
  "dependencies": {
    "cdx-plyer": "^1.0.2"
  }
}
```

---

## 🛠️ Usage

### 1. Plain HTML
Add this line to your `<head>`:

```html
<script src="https://dev.dubhub.lk/script/nirmal.js"></script>
```

**Basic Implementation**
```html
<!-- Playing a .cdx or .edu animation using URL -->
<nirmal-player 
    src="https://dev.dubhub.lk/anime/dev.cdx" 
    speed="1" 
    style="width:300px; height:300px;" 
    loop 
    autoplay>
</nirmal-player>
```

### 2. React / Next.js
If you installed via NPM, import it in your component or `_app.js`.

```javascript
import 'cdx-plyer';

function App() {
  return (
    <nirmal-player 
       src="https://dev.dubhub.lk/anime/dev.cdx" 
       autoplay 
       speed="1"
       style={{ width: '300px', height: '300px' }} 
    />
  );
}
```

---

## 💎 API Documentation

### Elements
You can use either of the following tags:
- `<nirmal-player>`

### Attributes
| Attribute | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| `src` | `String` | `null` | The URL of the `.json`, `.tgs`, or `.cdx` file. |
| `speed` | `Number` | `1` | Playback speed (e.g., `0.5`, `1.5`, `2`). |
| `loop` | `Boolean`| `false` | If present, the animation will restart once finished. |
| `autoplay` | `Boolean`| `false` | If present, starts playing immediately on load. |

---

## 📱 Flutter Implementation

You can also use Nirmal Player in your Flutter applications using our official `cdx_player` package.

### 📦 Installation (pub.dev)
Add this to your `pubspec.yaml`:

```yaml
dependencies:
  cdx_player: ^1.0.1
```

Then run:
```bash
flutter pub get
```

### 🛠️ Usage

#### Basic Implementation
```dart
import 'package:cdx_player/cdx_player.dart';

// Playing a .cdx animation from a URL
CdxPlayer(
  src: 'https://sticker-explorer.netlify.app/api/cdx?file_id=YOUR_ID',
  width: 300,
  height: 300,
)
```

#### Full Implementation
```dart
CdxPlayer(
  src: 'sticker.cdx',
  width: 250,
  height: 250,
  autoplay: true,
  loop: true,
  placeholder: CircularProgressIndicator(),
  errorWidget: Icon(Icons.error),
)
```

---

## 💡 Pro Tips

> [!TIP]
> **Performance:** For the smoothest experience, use `.cdx` or `.tgs` formats. They are compressed and take up to 80% less bandwidth than raw JSON.

> [!NOTE]
> **Dynamic Loading:** The player is smart! It checks if `lottie` is already present on the page. If not, it fetches a optimized version from Cloudflare CDN automatically.

> [!IMPORTANT]
> **Styling:** Always provide a `width` and `height` via CSS or the `style` attribute to prevent layout shifts.

---

## 🌈 Integration Example

Here is a full, beautiful example you can copy-paste into your project:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nirmal Player Showcase</title>
    
    <!-- Import Player -->
    <script src="https://dev.dubhub.lk/script/nirmal.js"></script>

    <style>
        body {
            background: radial-gradient(circle at center, #1a1a2e, #16213e);
            color: #fff;
            font-family: 'Inter', system-ui, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            margin: 0;
        }

        .card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 24px;
            padding: 40px;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(255, 255, 255, 0.1);
            text-align: center;
            transition: transform 0.3s ease;
        }

        .card:hover {
            transform: translateY(-5px);
        }

        h1 {
            margin-bottom: 30px;
            background: linear-gradient(to right, #00d2ff, #3a7bd5);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
    </style>
</head>
<body>

    <div class="card">
        <h1>Nirmal Player Test</h1>
        
        <!-- Nirmal Player Implementation -->
        <nirmal-player 
            src="https://dev.dubhub.lk/anime/dev.cdx" 
            speed="1" 
            style="width:300px; height:300px;" 
            loop 
            autoplay>
        </nirmal-player>

        <p style="opacity: 0.7; margin-top: 20px;">
            Smooth 60FPS Lottie Animation
        </p>
    </div>

</body>
</html>
```

---

## 🔍 More Animations

Need more beautiful CodeX (.cdx) animations? Visit our **Sticker Explorer**:
👉 **[https://sticker-explorer.netlify.app/](https://sticker-explorer.netlify.app/)**

---

## ⭐ Support Us

If you like this project, please don't forget to **Give a Star** on GitHub! It means a lot to us. 🌟🌟🌟

---

## 🔒 Optimized Format Support

- **.json:** Standard Lottie vectors.
- **.tgs:** Telegram Sticker Format (Gzipped JSON).
- **.cdx:** **CodeX** (New Generation Animation Style) — High-efficiency compressed formats.

---

---

© 2026 [K.Nirmal](https://dubhub.lk) | **K.Nirmal | Cyber Yakku | CodeX Developers**

Developed by K.Nirmal (CyberYakku)
For more stickers visit: [Sticker Explorer](https://sticker-explorer.netlify.app/)

**Keywords**
`lottie` `tgs` `cdx` `telegram-stickers` `animation` `player` `sticker-explorer`
