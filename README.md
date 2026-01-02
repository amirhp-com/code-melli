<img src="icon.svg" width="90" align="left" />

# 🇮🇷 Iranian National ID Validator & Generator

![Version](https://img.shields.io/badge/version-1.0.0-orange)
![License](https://img.shields.io/badge/license-MIT-blue)
![PWA](https://img.shields.io/badge/PWA-ready-success)
![RTL](https://img.shields.io/badge/RTL-supported-purple)

A beautiful, modern Progressive Web Application for validating and generating Iranian National ID numbers (کد ملی). Built with an Apple-inspired design aesthetic, featuring liquid glass effects and a dark orange theme.

[**Live Demo**](https://code-melli.netlify.app) • [**Report Bug**](https://github.com/amirhp-com/code-melli) • [**Developer Website**](https://amirhp.com/landing)

---

## ✨ Features

### 🔍 Validation
- **Real-time validation** of Iranian National ID numbers
- **Province detection** - automatically identifies the issuing province and city
- **Detailed feedback** - explains why an ID is invalid if applicable
- **Check digit verification** - implements the official algorithm

### 🎲 Generation
- **Generate valid test IDs** - creates structurally valid National IDs for testing
- **Province selection** - optionally generate IDs for specific provinces
- **One-click copy** - easily copy generated IDs to clipboard

### 🎨 Design
- **Dark mode** with orange accent colors
- **Liquid glass (Glassmorphism)** effects
- **Apple-inspired** UI/UX design language
- **Persian (Vazirmatn) font** for authentic RTL experience
- **Smooth animations** and micro-interactions
- **Responsive design** - works on all devices

### 📱 PWA Features
- **Installable** - add to home screen on any device
- **Offline capable** - works without internet connection
- **Fast loading** - cached assets for instant startup
- **Native feel** - full-screen standalone mode

---

## 🚀 Quick Start

### Deploy to Netlify

1. **Fork this repository** to your GitHub account

2. **Connect to Netlify:**
   - Go to [netlify.com](https://netlify.com) and sign in with GitHub
   - Click "Add new site" → "Import an existing project"
   - Select your forked repository
   - Configure build settings:
     - **Build command:** (leave empty)
     - **Publish directory:** `/`
   - Click "Deploy site"

3. **Enable automatic deploys:**
   - Netlify automatically deploys when you push to GitHub
   - Your site updates within seconds of each commit

### Local Development

```bash
# Clone the repository
git clone https://github.com/amirhp-com/code-melli.git

# Navigate to directory
cd iranian-national-id

# Serve locally (using any static server)
npx serve .
# or
python -m http.server 8000
```

---

## 🧮 Algorithm

The Iranian National ID (کد ملی) consists of 10 digits:

```
┌─────────────────┬──────────────────────┬─────────────┐
│   Digits 1-3    │      Digits 4-9      │  Digit 10   │
│  Province Code  │   Unique Identifier  │ Check Digit │
└─────────────────┴──────────────────────┴─────────────┘
```

### Check Digit Calculation

1. Multiply each of the first 9 digits by their weight (10 down to 2)
2. Sum all the products
3. Calculate: `remainder = sum % 11`
4. If `remainder < 2`: check digit = remainder
5. If `remainder >= 2`: check digit = 11 - remainder

### Example

For ID `0932833810`:

```
Position:  1    2    3    4    5    6    7    8    9
Digit:     0    9    3    2    8    3    3    8    1
Weight:   ×10  ×9   ×8   ×7   ×6   ×5   ×4   ×3   ×2
Result:    0   81   24   14   48   15   12   24    2

Sum = 0 + 81 + 24 + 14 + 48 + 15 + 12 + 24 + 2 = 220
220 % 11 = 0
Check digit = 0 ✓
```

---

## 📁 Project Structure

```
iranian-national-id/
├── index.html         # Main application (HTML, CSS, JS)
├── manifest.json      # PWA manifest
├── sw.js              # Service Worker for offline support
├── README.md          # Documentation
├── LICENSE            # MIT License
└── icons/
    ├── icon-72.png
    ├── icon-96.png
    ├── icon-128.png
    ├── icon-144.png
    ├── icon-152.png
    ├── icon-192.png
    ├── icon-384.png
    └── icon-512.png
```

---

## 🔐 Province Codes

The first 3 digits identify the issuing location. Examples:

| Code | Province | City |
|------|----------|------|
| 001-022 | اصفهان | Various cities |
| 168-171 | آذربایجان شرقی | Tabriz, etc. |
| 289-301 | تهران | Tehran districts |
| 500-521 | خراسان رضوی | Mashhad, etc. |
| 070-094 | فارس | Shiraz, etc. |

*Full mapping included in source code*

---

## ⚠️ Disclaimer

> **IMPORTANT: This tool is provided for educational and software testing purposes only.**
>
> The developer assumes **NO RESPONSIBILITY** for any misuse of this tool. Generated National IDs are structurally valid but are **NOT real identities**. Using generated IDs for fraud, identity theft, or any illegal purpose is strictly prohibited and may be punishable by law.
>
> **Use at your own risk.**

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Developer

**Amirhossein Hosseinpour**

- Website: [amirhp.com/landing](https://amirhp.com/landing)
- GitHub: [@amirhp-com](https://github.com/amirhp-com/)

---

<div align="center">

Made with 🧡 for the Iranian Developer Community

</div>
