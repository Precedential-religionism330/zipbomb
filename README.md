<div align="center">

```
 ______     __     ______   ______     ______     __    __     ______    
/\___  \   /\ \   /\  == \ /\  == \   /\  __ \   /\ "-./  \   /\  == \   
\/_/  /__  \ \ \  \ \  _-/ \ \  __<   \ \ \/\ \  \ \ \-./\ \  \ \  __<   
  /\_____\  \ \_\  \ \_\    \ \_____\  \ \_____\  \ \_\ \ \_\  \ \_____\ 
  \/_____/   \/_/   \/_/     \/_____/   \/_____/   \/_/  \/_/   \/_____/ 
```

# 💣 ZipBomb Generator

**A browser-based ZIP bomb generator — enter your unzip size and filename, download in one click.**

[![Live Demo](https://img.shields.io/badge/🌐%20Live%20Demo-GitHub%20Pages-38bdf8?style=for-the-badge)](https://anonymous-201.github.io/zipbomb/)
[![GitHub Repo](https://img.shields.io/badge/GitHub-anonymous--201%2Fzipbomb-181717?style=for-the-badge&logo=github)](https://github.com/anonymous-201/zipbomb)
[![License: MIT](https://img.shields.io/badge/License-MIT-22c55e?style=for-the-badge)](LICENSE)
[![Open Source](https://img.shields.io/badge/Open%20Source-❤️-ef4444?style=for-the-badge)](https://github.com/anonymous-201/zipbomb)
[![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-f59e0b?style=for-the-badge)](https://github.com/anonymous-201/zipbomb/pulls)

</div>

---

> ⚠️ **DISCLAIMER:** This tool is intended **strictly for educational and security research purposes only** — such as testing antivirus engines, decompression bomb detection, and understanding compression mechanics. **Do not** use this against any system you do not own or have explicit written permission to test. The author bears **no responsibility** for any misuse.

---

## 🌐 Live Demo

No installation needed — runs entirely in your browser:

👉 **[https://anonymous-201.github.io/zipbomb/](https://anonymous-201.github.io/zipbomb/)**

---

## 📸 Preview

> The tool features a clean dark UI where you input a ZIP filename and select your desired unzipped size (Bytes → Petabytes), then generate and download the ZIP bomb in one click.

---

## 📖 What is a ZIP Bomb?

A **ZIP bomb** (decompression bomb / zip of death) is a small archive file that expands to a massive size when extracted. They are used in security research to:

- Test how antivirus software handles malformed or extreme archives
- Stress-test file upload handlers and decompression pipelines
- Explore the limits of compression algorithms like DEFLATE

The key mechanic: null bytes (`\x00`) compress at ratios up to ~1000:1 — a 1 MB ZIP can unpack to 1 GB+.

---

## ✨ Features

| Feature | Details |
|---|---|
| 🎯 Custom unzip size | Choose from Bytes, KB, MB, GB, TB, or PB |
| 📁 Custom filename | Name your output ZIP anything you want |
| ⚡ One-click generation | Runs fully in-browser, no server needed |
| 🗜️ DEFLATE level 9 | Maximum compression for smallest output file |
| 🔒 No data sent anywhere | 100% client-side, nothing leaves your machine |
| 🌍 No install required | Open the HTML file or visit the GitHub Pages link |

---

## 🚀 Usage

### Option 1 — GitHub Pages (Recommended)

Visit the live site directly:
```
https://anonymous-201.github.io/zipbomb/
```

### Option 2 — Run Locally

```bash
# Clone the repository
git clone https://github.com/anonymous-201/zipbomb.git

# Open in browser
cd zipbomb
open index.html        # macOS
start index.html       # Windows
xdg-open index.html    # Linux
```

### How to Use

1. **Enter ZIP File Name** — type your desired output filename (e.g. `bomb`)
2. **Enter Unzipped Size** — type a number (e.g. `10`)
3. **Select Unit** — choose from `B`, `KB`, `MB`, `GB`, `TB`, or `PB`
4. Click **Generate & Download**
5. The `.zip` file downloads automatically to your machine

---

## 📂 Project Structure

```
zipbomb/
├── index.html       # Main tool — fully self-contained, no build step
├── README.md        # Project documentation
├── LICENSE          # MIT License
└── preview.png      # Screenshot for social previews (optional)
```

---

## ⚙️ How It Works

```
User Input (size + filename)
        │
        ▼
Uint8Array of null bytes (\x00) created in browser memory
        │
        ▼
JSZip compresses with DEFLATE level 9
        │
        ▼
Blob URL generated → <a> tag triggered → ZIP downloaded
```

- **Small sizes (B/KB/MB/GB ≤ 2GB):** Allocates exact byte count in memory, compresses to a single file.
- **Large sizes (TB/PB or GB > 2GB):** Uses a 50 MB base block repeated across multiple archive entries to stay within browser memory limits while reporting the full virtual size.

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

1. Fork the repo
2. Create your branch: `git checkout -b feature/my-feature`
3. Commit your changes: `git commit -m 'Add my feature'`
4. Push to the branch: `git push origin feature/my-feature`
5. Open a **Pull Request**

### Ideas for Contributions

- [ ] Add a progress bar for large file generation
- [ ] Support nested/recursive ZIP layers
- [ ] Dark/light theme toggle
- [ ] Add compression ratio display
- [ ] PWA support (offline use)

---

## 🛡️ Ethical Use Cases

- ✅ Testing antivirus and endpoint protection software
- ✅ Auditing file upload handlers for decompression bomb vulnerabilities
- ✅ Security research and CTF challenges
- ✅ Learning about DEFLATE and compression internals
- ✅ Penetration testing (with authorization)
- ❌ Attacking systems without permission — **strictly prohibited**

---

## 📜 License

This project is licensed under the **MIT License** — see [LICENSE](LICENSE) for details.

```
MIT License — Copyright (c) 2025 anonymous-201
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software to use, copy, modify, merge, and distribute it, subject to
the conditions in the LICENSE file.
```

---

## 👤 Author

**anonymous-201**
- 🌐 GitHub: [@anonymous-201](https://github.com/anonymous-201)
- 📦 Repo: [anonymous-201/zipbomb](https://github.com/anonymous-201/zipbomb)
- 🔗 Live Tool: [anonymous-201.github.io/zipbomb](https://anonymous-201.github.io/zipbomb/)

---

<div align="center">

Made with 💀 for the open-source security research community.

**⭐ If this was useful, please star the repo!**

[![Star History](https://img.shields.io/github/stars/anonymous-201/zipbomb?style=social)](https://github.com/anonymous-201/zipbomb/stargazers)

</div>
