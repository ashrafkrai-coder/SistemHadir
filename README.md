# suratamaran

Aplikasi Flutter Web/PWA untuk pengurusan kehadiran murid dan surat amaran.

## Deploy ke Vercel

Laluan deploy yang disyorkan untuk projek ini ialah build Flutter secara lokal, kemudian deploy output statik `build/web` ke Vercel.

### Keperluan

- Flutter SDK tersedia di `C:\Users\RAM1\flutter\bin\flutter.bat`
- Node.js dan Vercel CLI dipasang
- Sudah login Vercel melalui `vercel login`

### Preview deploy

```powershell
.\scripts\deploy-vercel.ps1
```

### Production deploy

```powershell
.\scripts\deploy-vercel.ps1 -Production
```

Skrip ini akan:

- membina `flutter build web --release`
- menyalin konfigurasi header PWA ke `build/web/vercel.json`
- deploy folder `build/web` terus ke Vercel

## Nota keselamatan

Password tidak lagi disimpan dalam browser local storage. Namun login aplikasi masih disahkan di sisi client melalui `lib/main.dart`, jadi credential itu masih boleh ditemui jika aplikasi dideploy secara public. Untuk production internet-facing, langkah seterusnya yang disyorkan ialah pindahkan autentikasi ke backend.
