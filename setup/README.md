# Laravel Application Setup

This is the main Laravel application directory.

## Quick Start

```bash
# Install dependencies
composer install
npm install

# Setup environment
cp .env.example .env
php artisan key:generate

# Run migrations
php artisan migrate

# Start development server
php artisan serve
```

## Project Structure

- `app/` - Application logic
- `config/` - Configuration files
- `database/` - Migrations and seeders
- `public/` - Web accessible files
- `resources/` - Views, assets, and language files
- `routes/` - Route definitions
- `storage/` - Generated files and logs
- `tests/` - Test files

## Development Commands

```bash
# Clear caches
php artisan optimize:clear

# Run tests
php artisan test

# Generate IDE helper files
php artisan ide-helper:generate
```

For detailed documentation, see the main README.md in the project root.
