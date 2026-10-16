# Seven Elements% — Minecraft Speedrun Leaderboard

Website starter untuk kategori Seven Elements%. Frontend ini berisi leaderboard, form submit run, rules, status pending/verified, dan tampilan world record.

## Jalankan demo lokal
Buka `index.html` di browser. Tanpa konfigurasi backend, submission disimpan di local storage browser itu saja. Data demo tidak terlihat oleh runner lain.

## Aktifkan leaderboard publik dengan Supabase
1. Buat project di https://supabase.com/
2. Buka SQL Editor dan jalankan isi `schema.sql`.
3. Di Supabase, buka Project Settings → API. Salin Project URL dan anon/public key.
4. Buka `index.html`, cari bagian:
   `const SUPABASE_URL = "";`
   `const SUPABASE_ANON_KEY = "";`
   lalu masukkan nilai project milikmu.
5. Deploy folder ini ke static hosting seperti Netlify, Vercel, atau GitHub Pages.
6. Uji submit run. Submission masuk sebagai `pending`; leaderboard publik hanya menampilkan run `verified`.

## Verifikasi run
Untuk versi starter ini, owner harus memeriksa video dan mengubah status menjadi `verified` atau `rejected` melalui Supabase Table Editor. Jangan pernah memasukkan service_role key ke file frontend. Anon key memang dirancang untuk frontend; keamanan data bergantung pada RLS policies dalam `schema.sql`.

## Elemen yang diwajibkan
- Tanah: Dirt
- Petir: Lightning Rod
- Air: Water Bucket
- Daun: Oak Leaves
- Cahaya: Glowstone
- Api: Fire Charge
- Angin: Wind Charge

## Ruleset yang ditampilkan
Minecraft Java Edition, singleplayer Survival, Random Seed, vanilla; tanpa cheat/command, mod gameplay, duplikasi item, atau reload backup. Timer berjalan selama run. Finish saat semua tujuh item ada di inventory secara bersamaan.

## Catatan
- Starter ini belum punya akun pengguna atau moderator panel khusus.
- Untuk leaderboard kompetitif, sebaiknya tetapkan satu versi Minecraft utama atau pisahkan kategori per versi.
- Pastikan aturan Oak Leaves (harus diperoleh sebagai item) dan format bukti video dijelaskan di halaman aturan.
