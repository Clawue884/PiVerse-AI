API_CONTRACT.md

PiVerse AI — API Contract Specification

Dokumen ini mendefinisikan kontrak API antara Frontend, Backend, dan AI Layer pada PiVerse AI.

Tujuan utama API Contract ini adalah memastikan komunikasi yang konsisten, aman, terukur, dan mudah diaudit.


---

🎯 Prinsip Desain API

Stateless

JSON-based

Non-custodial

Tidak menangani data sensitif

Mudah dikembangkan & diuji



---

🧩 Arsitektur API (High Level)

Frontend (React / Next.js)
        ↓ HTTPS
Backend API (Node.js / Python)
        ↓ Internal Call
AI Layer (Governor + Agents)


---

🔐 Authentication & Authorization

PiVerse AI tidak mewajibkan autentikasi pengguna untuk penggunaan dasar.

Jika autentikasi digunakan (opsional):

API Key terbatas

Rate limiting

Tidak menyimpan identitas personal



---

📥 Request Structure

Endpoint Umum

POST /api/ai/query

Request Body

{
  "mode": "education | developer | security | community",
  "message": "string",
  "context": {
    "language": "id | en",
    "source": "web | mobile",
    "risk_hint": "low | medium | high"
  }
}


---

📤 Response Structure

{
  "status": "success | rejected | limited",
  "mode": "education | developer | security | community",
  "response": "string",
  "confidence": "high | medium | low",
  "policy_notes": "optional string"
}


---

⚠️ Error Handling

{
  "status": "error",
  "error_code": "POLICY_BLOCK | INVALID_INPUT | RATE_LIMIT",
  "message": "Human-readable explanation"
}


---

🧠 AI Layer Internal Contract

Backend → AI Layer:

{
  "intent": "classified_intent",
  "risk_level": "low | medium | high",
  "prompt": "sanitized prompt",
  "mode": "education | developer | security | community"
}

AI Layer → Backend:

{
  "decision": "allow | limit | reject",
  "final_output": "string",
  "risk_level": "low | medium | high",
  "notes": "internal"
}


---

🔀 Mode Behavior Rules

Mode	Tujuan	Batasan

Education	Edukasi umum	Non-spekulatif
Developer	Bantuan teknis	Tidak klaim internal
Security	Anti-scam	Tidak tuduh individu
Community	Klarifikasi	Netral



---

🛡️ Security Considerations

Input sanitization

Rate limiting

Prompt injection protection

No private key handling



---

🔄 Versioning

Versioning berbasis URL atau header

Contoh: /api/v1/ai/query



---

✅ Penutup

API Contract ini memastikan PiVerse AI:

> Terhubung dengan rapi, dikendalikan dengan aman, dan dikembangkan tanpa risiko tersembunyi.
