# TFA1 POS System

A basic four-page Point-of-Sale (POS) laboratory project built with CodeIgniter 4 and PHP. It demonstrates routes, controllers, views, navigation, and static PHP array data. It does not use a database.

## Requirements

- PHP 8.2 or later with the `intl` and `mbstring` extensions
- Composer
- A local web server such as XAMPP Apache

## Installation and configuration

The project uses the CodeIgniter 4 AppStarter package. To create a new copy:

```bash
composer create-project codeigniter4/appstarter TFA1
```

In `.env`, configure the local environment and base URL:

```ini
CI_ENVIRONMENT = development
app.baseURL = 'http://localhost/webtech/TFA1/'
```

Update `app.baseURL` if you use a different local location. Configure a virtual host to point to `public` when possible.

## Run the application

Start Apache in XAMPP and open `http://localhost/webtech/TFA1/`. The root `.htaccess` file forwards requests to CodeIgniter's `public` directory, allowing clean URLs such as `/webtech/TFA1/users`. Alternatively, run this command from the project folder:

```bash
php spark serve
```

Use the local URL printed by CodeIgniter.

## Routes

| Route | Purpose |
| --- | --- |
| `/` | POS landing page |
| `/about` | Project information |
| `/customers` | Customer account listing |
| `/users` | Staff user account listing |

## MVC structure and data

- `app/Config/Routes.php` maps URLs to controller methods.
- `app/Controllers/Pages.php`, `Customers.php`, and `Users.php` prepare page data.
- `app/Views/` renders the pages; shared header and footer views provide navigation.

Customer and user records are static PHP arrays in their respective controllers. Each listing view receives its array and renders it with a `foreach` loop. No database, model, migration, or external API is used.

## Browser testing checklist

1. Open `/`, `/about`, `/customers`, and `/users`.
2. Confirm every page loads and navigation works on each page.
3. Confirm `/customers` shows five customer records and `/users` shows five staff records.
4. Confirm the configured base URL matches the browser address.
