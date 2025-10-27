🌐 Proxy List Repository
Koleksi proxy server yang siap dipakai untuk kebutuhan development, testing, maupun integrasi dengan aplikasi lain. List ini disajikan dalam format IP:Port sederhana agar mudah di-parse oleh script, bot, atau Cloudflare Worker.

📂 Struktur Repository
proxy.txt → Daftar proxy dalam format plain text (ip:port per baris).

proxy.json → Daftar proxy dalam format JSON array (opsional).

README.md → Dokumentasi repository.

🚀 Cara Menggunakan
1. Akses langsung via GitHub Raw
Proxy list bisa langsung diakses melalui link raw GitHub:

bash
curl -s https://raw.githubusercontent.com/kdean0759-lab/peroxi/main/proxyList.txt

2. Integrasi dengan Cloudflare Worker
Contoh Worker sederhana untuk serve ulang proxy list:

js
export default {
  async fetch(request) {
    const url = "https://raw.githubusercontent.com/kdean0759-lab/peroxi/main/proxyList.txt";
    const resp = await fetch(url);
    const text = await resp.text();

    return new Response(text, {
      headers: { "Content-Type": "text/plain" }
    });
  }
}
🔧 Format Proxy
Plain text:

Code
47.74.254.191:8900
129.150.58.86:57621
146.235.18.248:45137
JSON (opsional):

json
[
  "47.74.254.191:8900",
  "129.150.58.86:57621",
  "146.235.18.248:45137"
]
📌 Catatan
Proxy ini ditujukan untuk keperluan edukasi, riset, dan testing.

Gunakan secara bijak dan sesuai hukum yang berlaku.

Update list dilakukan secara manual/otomatis sesuai kebutuhan.

⭐ Dukungan
Kalau repo ini bermanfaat, jangan lupa kasih star ⭐ di GitHub!
