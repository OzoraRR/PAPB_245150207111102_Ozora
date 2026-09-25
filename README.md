## Implementasi state

`StateLabApp()` menyimpan `count`, `isRed`, dan `isFollowed` memakai `remember { mutableStateOf(...) }`. Nilainya menjadi sumber kebenaran untuk UI: ketika berubah, Compose melakukan recomposition pada bagian tampilan yang membaca nilai tersebut. Counter membatasi pengurangan dengan `coerceAtLeast(0)`. Kotak warna memilih warna dari `isRed` dan mengubahnya lewat `clickable`.

`ProfileCard` menerima `isFollowed` dan `onToggleFollow` sebagai parameter. Komponen ini tidak menyimpan state internal. Pola state hoisting tersebut membuat profil mudah digunakan kembali dan diuji dengan nilai serta callback yang berbeda.

State menggunakan `remember`, sehingga disimpan selama Composable masih aktif dan dapat hilang saat Activity dibuat ulang atau aplikasi ditutup. Penyimpanan lintas proses/aplikasi membutuhkan mekanisme lain seperti `rememberSaveable` atau penyimpanan persisten.

## Mengapa Compose lebih sederhana dibandingkan XML

Pada Compose, layout, state, dan aksi ditulis bersama sebagai fungsi Kotlin deklaratif. Label tombol, teks status, dan warna kotak langsung diturunkan dari state yang sama. Tidak perlu mencari view memakai ID, mengubah properti view secara manual, atau menyinkronkan model dan XML pada setiap klik. Komponen kecil juga dapat dipisah menjadi fungsi yang menerima state dan callback.

## Struktur penting

- `app/src/main/java/id/ac/ub/papb3state/MainActivity.kt` — UI Compose dan state.
- `app/src/main/res/drawable/profil.xml` — ilustrasi profil dummy.
- `screenshots/` — screenshot pada kondisi awal, warna hijau/counter, dan profil diikuti.
- `README.md` — penjelasan implementasi state dan perbandingan Compose dengan XML.
