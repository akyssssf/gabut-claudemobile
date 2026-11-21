# Gambar Gabut

Game tebak gambar ala Gartic untuk ramai-ramai (cocok 4–8 orang). Satu orang menggambar, yang lain menebak. Di bawah ada kartu "Bahan Ngobrol" (pilih A/B atau pertanyaan "kenapa?").

## Cara main
1. Buka link, langsung masuk (nama acak, bisa diganti di lobby).
2. Kalau sudah ada minimal 2 pemain, siapa pun boleh pencet **Mulai**.
3. Tiap ronde: pilih kata → gambar 40 detik → yang lain menebak. Makin cepat benar, makin banyak poin.

## Hosting di GitHub Pages
File yang dipakai cuma `index.html` dan `mqtt.min.js` (tanpa build).

1. Di GitHub: **Settings → Pages → Build and deployment**.
2. Source: **Deploy from a branch**, pilih branch (mis. `main`) dan folder `/ (root)`, lalu Save.
3. Tunggu 1–2 menit, link-nya muncul di halaman yang sama: `https://<user>.github.io/<repo>/`.

Semua yang membuka link yang sama otomatis masuk ke satu room. Mau room terpisah? Tambahkan `#nama-room` di ujung link, misalnya `.../gabut-claudemobile/#geng-kita`.

Di luar claude.ai, game memakai broker MQTT publik (`broker.emqx.io`, cadangan `broker.hivemq.com` dan `test.mosquitto.org`) lewat WebSocket sebagai jalur realtime. Isinya hanya nama panggilan, gerakan gambar, dan tebakan. Karena brokernya publik, pakai nama room yang susah ditebak untuk grup yang privat.

## Catatan
- Pemain paling awal masuk jadi host (👑). Kalau host keluar, host pindah otomatis ke pemain berikutnya.
- Pemain yang masuk di tengah ronde tidak melihat gambar yang sudah tergambar, hanya garis baru.
- Reload halaman menghapus skor pemain itu.
