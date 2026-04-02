🚀 1. Mulai dari Setup Project Laravel

Pertama, buat project Laravel dulu:

composer create-project laravel/laravel nama-project
cd nama-project

Atau kalau pakai installer:

laravel new nama-project
📁 2. Inisialisasi Git (WAJIB sebelum coding jauh)

Masuk ke folder project:

git init

Lalu cek apakah sudah ada .gitignore

👉 Laravel sudah menyediakan .gitignore default — ini sudah best practice.

Yang penting:

vendor/ ❌ jangan di-commit
.env ❌ jangan di-commit
node_modules/ ❌ jangan di-commit
⚙️ 3. Setup .env

Copy dari contoh:

cp .env.example .env
php artisan key:generate

⚠️ Best practice:

.env tidak pernah masuk GitHub
kalau perlu, buat .env.example versi clean
📦 4. First Commit (Initial Commit)

Setelah itu:

git add .
git commit -m "Initial commit - fresh Laravel setup"
🌐 5. Hubungkan ke GitHub

Buat repo baru di GitHub (kosong, tanpa README dulu)

Lalu:

git remote add origin https://github.com/username/nama-repo.git
git branch -M main
git push -u origin main
🌿 6. Gunakan Branching Strategy

Jangan kerja langsung di main 🚫

Best practice sederhana:

main → production (stabil)
develop → development
feature/* → fitur baru

Contoh:

git checkout -b develop
git push -u origin develop

Kalau bikin fitur:

git checkout -b feature/login
🧱 7. Struktur Coding Laravel (Best Practice)

Jangan semua logic di Controller ❌

Pisahkan:

Controller → handle request
Service → logic bisnis
Repository → query database (optional)
Request → validasi

Contoh struktur:

app/
 ├── Http/Controllers
 ├── Services
 ├── Repositories
 ├── Models
📝 8. Gunakan Commit yang Jelas

Jangan commit kayak:

fix
update

Gunakan format:

feat: add login feature
fix: fix validation bug on register
refactor: move logic to service layer
🔐 9. Jangan Upload Data Sensitif

Pastikan ini tidak pernah ke GitHub:

.env
API key
password database

Kalau sudah terlanjur → harus rotate credential 🔥

📚 10. README.md itu Penting

Isi minimal:

Deskripsi project
Cara install
Cara run

Contoh:

## Installation
- git clone
- composer install
- cp .env.example .env
- php artisan key:generate
- php artisan migrate
⚡ 11. Gunakan Migration (Jangan SQL Manual)

Laravel best practice:

php artisan make:migration create_users_table

👉 semua struktur DB harus lewat migration, bukan manual

🧪 12. (Opsional tapi penting) Testing

Laravel support:

php artisan test

Minimal:

test login
test API
🔁 13. Workflow Harian (Simple Version)

Pull latest:

git pull origin develop

Buat branch:

git checkout -b feature/nama-fitur
Coding

Commit:

git commit -m "feat: ..."

Push:

git push origin feature/nama-fitur
Pull Request ke develop
💡 Tips Tambahan (Advanced dikit)

Kalau mau lebih proper lagi:

pakai Laravel Sail (Docker)
pakai Prettier / Pint (formatter)
pakai CI/CD (GitHub Actions)

==============================================================================
php artisan serve
npm run dev