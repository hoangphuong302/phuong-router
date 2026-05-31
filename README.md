# 🛣️ phuong-router — Personal Fork của 9Router CLI

> **Fork cá nhân của 9Router CLI, tùy chỉnh cho Nhà Sam Aura ecosystem.**
> 9Router là công cụ CLI/proxy AI routing, cho phép tích hợp nhiều AI provider (OpenAI, Gemini, Anthropic...) qua 1 endpoint duy nhất.

[![GitHub](https://img.shields.io/badge/GitHub-phuong--router-blue)](https://github.com/hoangphuong302/phuong-router)
[![Upstream](https://img.shields.io/badge/Upstream-9router-gray)](https://github.com/decolua/9router)

---

## 🤖 Dành Cho AI Agent — Đọc Trước!

| Mục | Thông tin |
|---|---|
| **Dự án** | Personal fork của 9Router CLI |
| **GitHub** | `hoangphuong302/phuong-router` (fork của `decolua/9router`) |
| **Branch chính** | `main` |
| **Thư mục** | `C:\Workspace\my-9router` |
| **Chạy tại** | Port 20128 (9Router AI proxy server) |
| **PM2 app** | Không có (standalone CLI) |
| **Deploy action** | git pull → restart nếu đang chạy |

### ⚡ Quy Trình Cho AI Agent

```bash
# Sửa customizations (thường ở src/ hoặc app/)
# Commit và push
git add -A
git commit -m "v0.x.x: Custom AI routing cho Nhà Sam"
git push origin main

# → Server tự git pull
# → Restart 9router nếu đang chạy
```

### ⚠️ Đây là fork
- **Upstream**: `decolua/9router` — không sửa upstream code
- Chỉ sửa các file customization của `hoangphuong302`
- Sync từ upstream: `git pull upstream main`

---

## 🖥️ Infrastructure

```
[Windows PC - 100.112.62.110]
└── 9Router CLI (phuong-router)
    ├── Port 20128 (AI proxy)
    └── Tích hợp với AuraDashboard qua http://127.0.0.1:20128
```

9Router hoạt động như một AI API proxy:
- Nhận requests kiểu OpenAI API format
- Route đến provider phù hợp (Gemini, OpenAI, Anthropic...)
- Quản lý API keys tập trung

---

## 🔄 CI/CD — Auto Git Pull

Khi push lên GitHub:
1. Webhook trigger git pull
2. Deploy script `deploy-9router.cmd` kéo code mới
3. Nếu có PM2 app `phuong-router` → restart tự động

---

## 📋 Quy Trình Git

```bash
# Clone
git clone https://github.com/hoangphuong302/phuong-router.git my-9router
cd my-9router

# Thêm upstream (chỉ cần 1 lần)
git remote add upstream https://github.com/decolua/9router.git

# Sync từ upstream
git fetch upstream
git merge upstream/main

# Commit customizations
git add -A
git commit -m "v0.2.1: Thêm custom model routing cho Gemini Pro"
git push origin main
```

---

## 📁 Cấu Trúc File

```
my-9router/
├── cli.js          → CLI entry point
├── src/            → Source code
├── app/            → App logic/UI
├── hooks/          → PostInstall hooks
├── package.json    → Dependencies (name: phuong-router)
└── README.md
```

---

*Một phần của **Nhà Sam Aura** AI ecosystem.*
*README cập nhật lần cuối: 2026-05-31*
