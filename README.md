OWNER="Abdian21"
REPO="OurLoveCouple-Updates"
BRANCH="main"
FILE="README.md"

cat > /tmp/README.md <<'EOF'
<div align="center">

# 💞 OurLoveCouple

### Aplikasi couple pribadi untuk chat, kenangan, lokasi, catatan, keuangan, dan momen bersama pasangan.

<br>

![Version](https://img.shields.io/badge/version-1.0.9-ff7ab8?style=for-the-badge)
![Android](https://img.shields.io/badge/platform-Android-7db7ff?style=for-the-badge)
![Status](https://img.shields.io/badge/status-active-72d39a?style=for-the-badge)
![Made With Love](https://img.shields.io/badge/made%20with-love-b06cff?style=for-the-badge)

<br>

<a href="https://github.com/Abdian21/OurLoveCouple-Updates/releases/latest">
  <img src="https://img.shields.io/badge/Download_APK-OurLoveCouple-ff7ab8?style=for-the-badge&logo=android&logoColor=white" />
</a>

</div>

---

## ✨ Tentang Aplikasi

**OurLoveCouple** adalah aplikasi pasangan berbasis Android yang dibuat untuk membantu pasangan tetap terhubung lewat fitur chat, kenangan, lokasi, catatan, keuangan, profil pasangan, dan asisten AI.

Aplikasi ini dibuat dengan nuansa romantis, modern, dan premium agar nyaman dipakai setiap hari.

---

## 🌸 Fitur Utama

| Fitur | Keterangan |
|---|---|
| 💬 Chat Pasangan | Chat realtime dengan pasangan |
| 📍 Berbagi Lokasi | Melihat lokasi pasangan saat fitur lokasi aktif |
| 🖼️ Kenangan | Menyimpan foto dan momen spesial |
| 📝 Catatan | Membuat catatan pribadi/bersama |
| 💰 Keuangan | Mencatat keuangan sederhana |
| 🤖 Asisten AI | Bantuan AI di dalam aplikasi |
| 🔋 Status Baterai | Melihat status baterai pasangan saat tersedia |
| 👤 Profil Pasangan | Mengatur profil dan informasi hubungan |

---

## 📦 Download APK

### ➜ [Download OurLoveCouple APK](https://github.com/Abdian21/OurLoveCouple-Updates/releases/latest)

Versi saat ini:

### ➜ [OurLoveCouple 1.0.9](https://github.com/Abdian21/OurLoveCouple-Updates/releases/download/v1.0.9/OurLoveCouple-v1.0.9.apk)

---

## 🚀 Update 1.0.9

- Tampilan Login dan Register diperbarui.
- Splash Screen diperbarui.
- Ikon aplikasi diperbarui.
- Fix bug.

---

## 🔄 Sistem Update

Repository ini dipakai sebagai pusat update aplikasi **OurLoveCouple**.

File update: `update.json`

URL update:

`https://raw.githubusercontent.com/Abdian21/OurLoveCouple-Updates/main/update.json`

---

## 🛡️ Catatan

- Aplikasi hanya untuk pasangan yang saling terhubung.
- Fitur lokasi berjalan dengan izin pengguna.
- Download APK hanya dari repository ini agar aman.

---

<div align="center">

### 💖 OurLoveCouple

Dibuat untuk menyimpan cerita kecil yang berarti besar.

</div>
EOF

SHA=$(gh api "repos/$OWNER/$REPO/contents/$FILE?ref=$BRANCH" --jq .sha)
CONTENT=$(base64 -w 0 /tmp/README.md 2>/dev/null || base64 /tmp/README.md | tr -d '\n')

gh api --method PUT "repos/$OWNER/$REPO/contents/$FILE" \
  -f message="Update premium README" \
  -f branch="$BRANCH" \
  -f content="$CONTENT" \
  -f sha="$SHA"
