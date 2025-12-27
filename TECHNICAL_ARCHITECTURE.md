TECHNICAL_ARCHITECTURE.md

Arsitektur Teknis (High Level)

Dokumen ini menjelaskan arsitektur teknis tingkat tinggi PiVerse AI, mencakup komponen utama sistem, peran masing‑masing lapisan, serta prinsip desain yang digunakan.

Desain sistem PiVerse AI mengutamakan akurasi, netralitas, keamanan, dan kepatuhan terhadap ekosistem Pi Network.


---

🖥️ Frontend Layer

Teknologi:

React.js atau Next.js


Peran:

Antarmuka interaksi pengguna (UI/UX)

Menyediakan mode interaksi AI (Edukasi, Developer, Keamanan, Komunitas)

Menampilkan respons AI secara transparan & mudah dipahami


Karakteristik Desain:

Ringan & responsif

Tidak menyimpan data sensitif

Fokus pada edukasi & utilitas, bukan spekulasi



---

⚙️ Backend Layer

Teknologi:

Node.js atau Python


Peran:

Mengelola request dari frontend

Melakukan intent classification awal

Menghubungkan frontend dengan AI Layer

Logging non‑sensitif untuk audit sistem


Karakteristik Desain:

Stateless

Modular

Mudah diaudit



---

🧠 AI Layer

Fungsi Utama:

Prompt routing berbasis mode & intent

Implementasi sistem Multi‑Agent

Enforcement kebijakan melalui Governor Agent


Komponen:

SYSTEM_PROMPT

ADVANCED_SYSTEM_PROMPT

Governor Agent

Specialized Agents (Knowledge, Developer, Security, Community)


Prinsip:

Policy‑first

Safety‑first

Non‑speculative



---

🔀 Prompt Routing System

Prompt routing menentukan agent & mode yang digunakan berdasarkan:

Jenis pertanyaan

Tingkat risiko

Konteks pengguna


Contoh mode:

Edukasi Umum

Developer Support

Security & Anti‑Scam

Community Clarification


Routing selalu divalidasi oleh Governor Agent sebelum dan sesudah eksekusi.


---

📚 Knowledge Base Layer

Format:

Markdown (.md)

JSON terstruktur


Isi:

Dokumentasi Pi Network (publik)

Panduan edukatif

Klarifikasi komunitas

FAQ non‑spekulatif


Karakteristik:

Dikurasi manual

Tidak menggunakan sumber tidak resmi

Mudah diperbarui & diaudit



---

🛡️ Security & Compliance Layer

Lapisan ini bersifat lintas‑sistem dan mencakup:

Input filtering

Anti prompt‑injection

Penolakan spekulasi harga & ROI

Proteksi data pengguna

Kepatuhan kebijakan Pi Network



---

🔗 High‑Level Data Flow

User
 ↓
Frontend (React / Next.js)
 ↓
Backend (Node.js / Python)
 ↓
Intent Classification
 ↓
Governor Agent
 ↓
Specialized Agent
 ↓
Governor Validation
 ↓
Response to User


---

🎯 Prinsip Desain Utama

Akurasi di atas kecepatan

Netralitas di atas narasi

Keamanan di atas fitur

Kepatuhan di atas popularitas



---

✅ Penutup

Arsitektur teknis ini memastikan PiVerse AI:

> Terukur secara teknis, aman secara etis, dan selaras dengan ekosistem Pi Network.
