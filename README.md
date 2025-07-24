# Laravel Application

A modern Laravel web application with Nginx and MySQL setup.

## 🚀 Project Overview

This Laravel application is configured with:
- **Framework**: Laravel 10.x (Upgrade to 11.x recommended)
- **PHP**: 8.1+ (8.3 recommended)
- **Web Server**: Nginx with PHP-FPM
- **Database**: MySQL
- **Environment**: Production-ready setup

## 📋 Prerequisites

- PHP 8.1+ (8.3 recommended)
- Composer
- MySQL 8.0+
- Nginx
- Node.js & NPM (for frontend assets)

## 🛠️ Installation & Setup

### 1. Clone and Install Dependencies
```bash
git clone <repository-url>
cd laravel/setup
composer install
npm install
```

### 2. Environment Configuration
```bash
cp .env.example .env
php artisan key:generate
```

### 3. Database Setup
```bash
# Configure database in .env file
php artisan migrate
php artisan db:seed
```

### 4. File Permissions
```bash
sudo chown -R www-data:www-data storage bootstrap/cache
chmod -R 775 storage bootstrap/cache
```

### 5. Nginx Configuration
```bash
# Copy nginx configuration
sudo cp nginx/myLaravelApp.conf /etc/nginx/sites-available/
sudo ln -s /etc/nginx/sites-available/myLaravelApp.conf /etc/nginx/sites-enabled/
sudo nginx -t
sudo systemctl reload nginx
```

## 🔧 Development Commands

```bash
# Start development server
php artisan serve

# Run migrations
php artisan migrate

# Clear caches
php artisan config:clear
php artisan cache:clear
php artisan view:clear

# Generate application key
php artisan key:generate

# Run tests
php artisan test
```

## 📦 Recommended Packages

### Development Tools
- `laravel/telescope` - Application debugging
- `barryvdh/laravel-debugbar` - Debug toolbar
- `laravel/pint` - Code style fixer

### Production Enhancements
- `laravel/horizon` - Queue monitoring
- `spatie/laravel-permission` - Role management
- `laravel/sanctum` - API authentication
- `predis/predis` - Redis support

## 🚀 Deployment

### Production Optimization
```bash
composer install --optimize-autoloader --no-dev
php artisan config:cache
php artisan route:cache
php artisan view:cache
npm run build
```

### Queue Workers
```bash
# Start queue worker
php artisan queue:work

# Supervisor configuration recommended for production
```

## 🔒 Security Checklist

- [ ] Environment variables secured
- [ ] Database credentials protected
- [ ] HTTPS enabled
- [ ] CSRF protection active
- [ ] Input validation implemented
- [ ] File upload restrictions
- [ ] Rate limiting configured

## 📊 Performance Optimization

### Caching Strategy
- **Config Cache**: `php artisan config:cache`
- **Route Cache**: `php artisan route:cache`
- **View Cache**: `php artisan view:cache`
- **Redis**: For sessions and cache
- **OPcache**: PHP bytecode caching

### Database Optimization
- Index optimization
- Query optimization
- Database connection pooling
- Read/write splitting for high traffic

## 🧪 Testing

```bash
# Run all tests
php artisan test

# Run specific test suite
php artisan test --testsuite=Feature
php artisan test --testsuite=Unit

# Generate coverage report
php artisan test --coverage
```

## 📝 API Documentation

If this project includes APIs:
- Use Laravel Sanctum for authentication
- Implement API versioning
- Add rate limiting
- Document with OpenAPI/Swagger

## 🔄 Upgrade Path

### Laravel 10 → 11 Migration
1. Update `composer.json` requirements
2. Run `composer update`
3. Update deprecated methods
4. Test thoroughly
5. Update documentation

### PHP 8.1 → 8.3 Migration
1. Install PHP 8.3
2. Update Nginx/Apache configuration
3. Test application compatibility
4. Update composer requirements

## 🐛 Troubleshooting

### Common Issues
- **Permission errors**: Check file ownership and permissions
- **Database connection**: Verify .env database settings
- **Nginx 502**: Check PHP-FPM service status
- **Composer errors**: Clear composer cache

### Logs Location
- Laravel: `storage/logs/laravel.log`
- Nginx: `/var/log/nginx/error.log`
- PHP-FPM: `/var/log/php8.1-fpm.log`

## 📞 Support

For issues and questions:
- Check Laravel documentation: https://laravel.com/docs
- Review application logs
- Check system requirements
- Verify server configuration


