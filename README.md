# CheatEngine Evo 🎮

Automated build & release pipeline for [Cheat Engine](https://github.com/cheat-engine/cheat-engine) — tự động lấy source CE mới nhất, build và phát hành qua GitHub Releases.

## ✨ Tính năng

- 🔄 **Tự động kiểm tra** phiên bản CE mới mỗi ngày (00:00 UTC)
- 🏗️ **Build tự động** từ source code chính thức bằng Lazarus/FPC
- 📦 **Tạo Release** tự động trên GitHub với file ZIP
- 🪟 **Windows** (32-bit & 64-bit) — *Các nền tảng khác sắp ra mắt*

## 🚀 Cách dùng

### Chạy thủ công
1. Vào tab **Actions** trên GitHub
2. Chọn workflow `Build & Release CheatEngine (Windows)`
3. Nhấn **Run workflow**
4. (Tuỳ chọn) Tick `Force rebuild` để build lại dù đã có version đó

### Tự động (mặc định)
Workflow tự chạy mỗi ngày. Nếu CE có version mới → build & release tự động.

## 📁 Cấu trúc

```
.github/
└── workflows/
    └── build-release.yml   # Workflow chính
```

## ⚙️ Workflow Jobs

```
check-version → build-windows → create-release
```

| Job | Mô tả |
|-----|-------|
| `check-version` | Gọi GitHub API, lấy tag mới nhất của CE |
| `build-windows` | Clone source, cài Lazarus, build 32/64-bit |
| `create-release` | Tạo Release với file ZIP đính kèm |

## 🔗 Links

- **Source gốc:** https://github.com/cheat-engine/cheat-engine
- **Releases:** https://github.com/JkarVN/CheatEngineEvo/releases
