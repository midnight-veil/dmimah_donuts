# dmimah_donuts
Website for D'Mimah Donuts

## Docker — Setup & Jalankan

Persyaratan:

- Docker dan Docker Compose terpasang di mesin Anda.

Langkah singkat (production):

```bash
# build dan jalankan service produksi (exposes port 3000)
docker-compose up --build web -d

# lihat log jika perlu
docker-compose logs -f web

# hentikan
docker-compose down
```

Langkah pengembangan (live reload):

```bash
# jalankan service dev (bind ke host 0.0.0.0 -> akses dari browser host)
docker-compose up --build dev
```

Catatan penting:

- Aplikasi ini menggunakan Next.js — pastikan `package.json` memiliki script `build` (biasanya `next build`) dan `start` (`next start`). Dockerfile menjalankan `npm run build` lalu `npm run start` pada port `3000`.
- Jika Anda ingin serve static export (`next export`) dan memakai Nginx, beri tahu saya supaya saya buat varian Dockerfile statis.
- Jika tampilan yang muncul masih default React/Vite page, pastikan project benar-benar Next.js dan `npm run build` menghasilkan aplikasi Next yang benar.

Contoh periksa script di `package.json`:

```json
{
	"scripts": {
		"dev": "next dev",
		"build": "next build",
		"start": "next start"
	}
}
```

Jika mau, saya bisa commit perubahan ini ke branch baru dan push, atau buat ZIP berisi perubahan. Beri tahu preferensi Anda.

