## 🚀 Installation Guide

### Steps
1. Clone the repository
```bash
git clone https://github.com/glCoder8/haven-hopper.git
cd haven-hopper
```

2. Install dependencies
```bash
composer install
npm install
```

3. Configure environment variables
```bash
cp .env.example .env
php artisan key:generate
```

4. Run migrations:
```bash
php artisan migrate
```

5. Set up storage:
```bash
php artisan storage:link
```

6. Start the development server:
```bash
php artisan serve
```

7. Start asset compilation:
```bash
npm run dev
```

