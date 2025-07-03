# Struktur Folder React

## Node_modules
node_modules adalah folder di mana semua dependensi proyek (pustaka, frameworks, tools, dll). Ketika menjalankan ```npm install``` atau ```yarn install``` semua package yang tercantum dalam package.json akan diunduh dan ditempatkan di sini.

## Public
Public adalah Folder yang biasanya berisi aset statis yang akan disalin langsung ke direktori output saat proses build tanpa diproses oleh bundler (seperti Vite).

## src
Src singakatan dari source (sumber). src adalah folder utama di mana semua kode sumber aplikasi berada. Semua komponen React, logika bisnis, styling, dan berkas-berkas penting lainnya akan ditempatkan disini. 

## .gitinore
.gitinore adalah berkas konfigurasi untuk Git. Ini berisi daftar nama berkas dan folder yang harus diabaikan oleh Git, artinya berkas-berkas tersebut tidak akan dilacak atau dimasukkan ke dalam repositori.\
**Fungsi utama:** Mencegah ```node_modules/``` dan berkas-berkas yang dihasilkan saat build (seperti folder ```dist/``` atau ```build/```) untuk masuk ke repositori. Juga bisa mengecualikan berkas sensitif seperti ```.env```.

## eslint.config.js
```eslint.config.js``` Berkas konfigurasi untuk ESLint. ESLint adalah alat linting yang membantu mengidentifikasi dan melaporkan pola-pola bermasalah yang ditemukan dalam kode JavaScript/TypeScript. Ini digunakan untuk menjaga konsistensi gaya kode dan mencegah bug umum.\
**Fungsi:** Mendefinisikan aturan linting, lingkungan, parser, dan plugin yang digunakan untuk menganalisis kode.

## index.html
```index.html``` Ini adalah berkas HTML utama aplikasi Anda. Ini adalah halaman web kosong yang akan diisi oleh aplikasi React Anda.
**Penting:** Biasanya hanya berisi satu elemen ```<div id="root"></div>``` (atau serupa) di mana aplikasi React akan di-mount (ditempelkan). Ini adalah titik awal yang diakses oleh browser.

## package-lock.json
```package-lock.json``` Dibuat secara otomatis oleh npm (atau yarn.lock jika menggunakan Yarn). Berkas ini mencatat versi pasti dari setiap dependensi (termasuk sub-dependensi) yang diinstal di node_modules.\
**Fungsi:** Memastikan bahwa siapa pun yang menginstal proyek Anda akan mendapatkan versi dependensi yang persis sama, yang sangat penting untuk konsistensi dan mencegah masalah "berfungsi di mesin saya".

## package.json
```package.json``` Ini adalah "manifest" atau "identitas" proyek Anda. Ini berisi metadata tentang proyek dan, yang paling penting, daftar semua dependensi proyek (pustaka yang dibutuhkan) dan script yang bisa dijalankan.\
**Isi penting:**
- **name:** Nama proyek.
- **version:** Versi proyek.
- **dependencies:** Dependensi yang dibutuhkan untuk menjalankan aplikasi di produksi.
- **devDependencies:** Dependensi yang hanya dibutuhkan selama pengembangan (misalnya, tools seperti ESLint, Vite).
- **scripts:** Perintah yang dapat Anda jalankan, seperti npm start, npm run build, npm test.

## README.md
```README.md``` Berkas teks ini berisi informasi tentang proyek, biasanya ditulis dalam format Markdown (.md).\
**Fungsi:** Memberikan panduan tentang cara menginstal, menjalankan, menguji, dan berkontribusi pada proyek. Ini adalah halaman pertama yang akan dilihat oleh pengembang lain atau bahkan diri Anda sendiri di masa depan ketika menjelajahi repositori Git.

## tsconfig.app.json, tsconfig.json, tsconfig.node.json
Semua ini adalah berkas konfigurasi untuk TypeScript. TypeScript adalah superset JavaScript yang menambahkan pengetikan statis, memungkinkan Anda mendeteksi kesalahan lebih awal.\
**Fungsi:** Berkas-berkas ini memberitahu kompiler TypeScript bagaimana mengompilasi kode TypeScript Anda ke JavaScript biasa, termasuk opsi-opsi seperti target ES version, module system, JSX support, dll.\
Pemisahan: Seringkali ada beberapa tsconfig untuk tujuan yang berbeda:
- **```tsconfig.json```:** Konfigurasi dasar untuk proyek secara keseluruhan.
- **```tsconfig.app.json```:** Konfigurasi spesifik untuk kode aplikasi yang akan di-build untuk browser.
- **```tsconfig.node.json```:** Konfigurasi spesifik untuk kode yang berjalan di lingkungan Node.js (misalnya, untuk backend, build scripts, atau tests yang menggunakan Node.js). Ini membantu memastikan TypeScript mengerti lingkungan eksekusi yang berbeda.

## vite.config.ts
```vite.config.ts``` Berkas konfigurasi untuk Vite. Vite adalah build tool dan development server modern yang dirancang untuk kecepatan dan kinerja tinggi.\
**Fungsi:** Berkas ini mendefinisikan bagaimana Vite harus memproses proyek Anda, termasuk plugins yang digunakan (misalnya, plugin React untuk Vite), proxy settings, alias paths, dan konfigurasi lainnya yang mempengaruhi proses development dan build. Ekstensi .ts menunjukkan bahwa berkas konfigurasi ini ditulis dalam TypeScript.

# Objek-Objek React
- **```{ StrictMode }```:** Ini adalah "named import". Artinya, kita mengimpor sesuatu yang secara spesifik diberi nama StrictMode dari modul react. StrictMode adalah sebuah komponen pembungkus (wrapper component) yang disediakan oleh React.
- **```StrictMode```:** Ini adalah alat pengembangan yang membantu Anda menemukan potensi masalah dalam aplikasi Anda. Ini akan mengaktifkan pemeriksaan tambahan dan peringatan untuk praktik-praktik yang tidak disarankan di React. Penting: ini hanya berjalan dalam mode pengembangan dan tidak akan memengaruhi kinerja atau perilaku aplikasi Anda di produksi.
- **```react-dom/client```**: Ini adalah package React khusus untuk berinteraksi dengan DOM (Document Object Model) di browser (bagian client).
- **```createRoot```**: Ini adalah fungsi baru di React 18 (dan versi yang lebih baru) yang digunakan untuk membuat "root" di mana aplikasi React Anda akan di-render. Ini adalah cara modern dan direkomendasikan dibandingkan dengan ReactDOM.render() yang lebih lama, karena mendukung fitur-fitur baru seperti concurrent rendering dan suspense.
- **```!```** (Non-null assertion operator): Ini adalah fitur TypeScript. Tanda seru ini memberi tahu TypeScript bahwa Anda yakin document.getElementById('root') tidak akan pernah mengembalikan null atau undefined dalam skenario ini. Tanpa !, TypeScript mungkin akan mengeluh karena getElementById bisa saja mengembalikan null.
- **```.render(...)```:** Ini adalah metode yang dipanggil pada objek root yang baru dibuat. Ini memberitahu React untuk mulai me-render "elemen React" yang diberikan sebagai argumen ke dalam elemen DOM yang diidentifikasi oleh root.
- **```useState```:** Ini adalah salah satu React Hooks. Hooks adalah fungsi khusus yang memungkinkan Anda "mengaitkan" (hook into) fitur React seperti state dan lifecycle dari komponen fungsional. Sebelum Hooks, ini hanya bisa dilakukan di komponen kelas.\
**Fungsi useState:** Digunakan untuk menambahkan state (data yang dapat berubah seiring waktu dan memicu re-render komponen) ke komponen fungsional.
- **```const [count, setCount] = useState(0)```** adalah contoh penggunaan hook useState. Ini adalah array destructuring.
  - ```useState(0):``` Memanggil useState dengan nilai awal 0.
  - **Mengembalikan array:** useState mengembalikan sebuah array dengan dua elemen:
  - ```count:``` Variabel state saat ini. Nilai awalnya adalah 0.
  - ```setCount:``` Fungsi setter. Fungsi ini digunakan untuk memperbarui nilai count. Ketika setCount dipanggil, React akan memperbarui state count dan memicu komponen untuk re-render dengan nilai count yang baru.
- **```return (...)```:** Fungsi komponen React harus mengembalikan elemen React (yang mirip dengan HTML tapi sebenarnya adalah JSX).
- **```<></>```** (Fragment): Ini adalah "Fragment" React. Ini memungkinkan Anda mengembalikan beberapa elemen dari sebuah komponen tanpa harus membungkusnya dalam satu elemen HTML tambahan (misalnya, satu ```<div>``` besar). Ini berguna untuk menghindari  ```<div>``` yang tidak perlu dalam struktur DOM Anda.
- **```className```:** Dalam JSX, kita menggunakan className alih-alih class untuk menentukan kelas CSS. Ini karena class adalah kata kunci yang dicadangkan di JavaScript.
- onClick: Ini adalah penanganan event (event handler) di React. Ini adalah prop yang menerima fungsi yang akan dieksekusi ketika elemen tersebut diklik.
- **```() => setCount((count) => count + 1)```:** Ini adalah fungsi panah (arrow function). Ketika tombol diklik, fungsi ini akan dipanggil. Di dalamnya, setCount dipanggil dengan sebuah fungsi yang menerima state count sebelumnya dan mengembalikan count + 1. Ini adalah cara yang direkomendasikan untuk memperbarui state ketika nilai baru bergantung pada nilai sebelumnya.
- **```{count} (JavaScript Expression)```**: Ini adalah cara untuk menyematkan (embed) ekspresi JavaScript di dalam JSX. Nilai dari variabel count akan ditampilkan langsung sebagai teks di dalam elemen ```<button>```.
- **```export default App```**: Ini adalah pernyataan JavaScript standar untuk mengekspor nilai App sebagai ekspor default dari berkas ini. Ini berarti ketika berkas lain mengimpor dari App.tsx (seperti yang dilakukan main.tsx), mereka akan mendapatkan komponen App secara default.
