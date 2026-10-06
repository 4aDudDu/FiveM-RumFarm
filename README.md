# FiveM RumFarm

FiveM RumFarm adalah resource sistem pertanian yang dibuat untuk server FiveM dengan framework QB-Core. Resource ini menyediakan fitur panen tanaman, hewan ternak, sistem jual hasil panen, serta marker/blip area pertanian untuk job `farmer`.

## Fitur

- Panen berbagai tanaman seperti padi, kopi, tebu, teh, jeruk, apel, kayu, garam, dan lainnya
- Spawning objek pertanian dan hewan secara dinamis di map
- Target interaction menggunakan `ox_target`
- Progress bar saat panen
- Skill check untuk beberapa item seperti kayu dan garam
- Sistem jual hasil panen ke NPC penjual
- Integrasi dengan inventory QB-Core
- Blip area pertanian di peta

## Dependencies

Pastikan resource berikut sudah tersedia di server Anda:

- `qb-core`
- `ox_lib`
- `bl_idcard`
- `ox_target`
- `ox_inventory`
- `qb-menu`
- `qb-input`

Catatan: resource ini juga memanggil `InteractSound` untuk efek suara saat memotong kayu (`chopwood`) apabila ingin suara terdengar lebih hidup.

## Struktur Folder

```text
FiveM-RumFarm/
├── client/
│   ├── cl_farm.lua
│   └── cl_jualan.lua
├── server/
│   ├── sv_farm.lua
│   └── sv_jualan.lua
├── config.lua
├── fxmanifest.lua
└── README.md
```

## Instalasi

1. Masuk ke folder server resources Anda, misalnya:

```bash
/resources/[local]/FiveM-RumFarm
```

2. Salin semua file repository ini ke folder tersebut.

3. Tambahkan resource pada `server.cfg`:

```cfg
ensure qb-core
ensure ox_lib
ensure bl_idcard
ensure ox_target
ensure ox_inventory
ensure qb-menu
ensure qb-input
ensure FiveM-RumFarm
```

4. Restart server FiveM Anda.

## Cara Pakai

1. Pastikan karakter Anda memiliki job `farmer`.
2. Masuk ke area pertanian yang muncul di peta.
3. Gunakan target interaction pada tanaman atau hewan untuk panen.
4. Setelah mendapat hasil panen, buka NPC penjual yang tersedia untuk menjual barang.
5. Masukkan jumlah item yang ingin dijual pada menu popup.

## Konfigurasi

File utama konfigurasi ada di `config.lua`.

Beberapa bagian yang bisa disesuaikan:

- `Config.Farming` untuk daftar item, prop, lokasi tanaman, dan hewan
- `Config.SellerPed` untuk NPC penjual
- `Config.SellableItems` untuk daftar item yang bisa dijual beserta harga per item

Contoh:

```lua
Config.SellerPed = {
    model = "cs_bankman",
    coords = vector4(-383.24, 1194.8, 325.0, 75.99),
    scenario = "WORLD_HUMAN_CLIPBOARD"
}
```

```lua
Config.SellableItems = {
    { name = "biji_kopi", label = "Biji Kopi", price = 400 },
    { name = "tebu", label = "Tebu Gula", price = 600 },
    { name = "jeruk", label = "Buah Jeruk", price = 800 },
}
```

## Catatan Penting

- Resource ini dirancang untuk kebutuhan server berbasis QB-Core.
- Jika Anda ingin mengubah lokasi panen atau menambah item baru, silakan edit pada `config.lua`.
- Pastikan nama item inventory sesuai dengan item yang ada di server Anda, terutama saat menambah item baru.

## Credits

- Resource ini dibuat dan dikembangkan oleh `RyanDEV`.
- Didesain untuk kebutuhan roleplay farming di server FiveM.

## Lisensi

Silakan sesuaikan lisensi sesuai kebutuhan proyek Anda jika ingin dipublikasikan atau dikembangkan lebih lanjut.
