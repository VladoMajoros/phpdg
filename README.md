# phpdg v0.5.0

🚀 **PHP Documentation Generator** - Automatically generates beautiful HTML documentation from PHP files with DocBlock support.

## ✨ Features

- ✅ Recursive directory scanning
- ✅ Parses PHP classes, functions, and methods
- ✅ Full PHPDoc comment support (@param, @return, @description)
- ✅ Interactive tree structure navigation
- ✅ Modern dark theme UI (VS Code inspired)
- ✅ **NEW: Source code viewer with AJAX loading**
- ✅ HTTP authentication with .htaccess
- ✅ Multi-language support with language picker (10 languages)
- ✅ **NEW: RTL support for right-to-left languages**
- ✅ Expandable/collapsible method details
- ✅ Real-time search functionality
- ✅ Collapsible directory tree on main page

## 📦 Requirements

- PHP 7.4 or higher
- Apache web server (for .htaccess authentication - optional)

## 🚀 Quick Start

### 1. Configuration

Edit the `$settings` array in `generator.php`:
```php
$settings = [
    // Directories to scan (recursive)
    'directories' => [
        '../your-project/app/Controllers',
        '../your-project/app/Models',
    ],
    
    // Output directory
    'output_dir' => 'output',
    
    // Exclude directories
    'exclude_dirs' => ['vendor', 'cache', 'node_modules'],
    
    // HTTP authentication (optional)
    'http_auth' => [
        // 'admin' => 'password123',
    ],
    
    // Language (en, sk, cs, de, pl, pt, ru, uk, hi, fa)
    'language' => 'en',
    
    // Available languages in documentation
    'available_languages' => ['en', 'sk', 'cs', 'de', 'pl', 'pt', 'ru', 'uk', 'hi', 'fa'],
];
```

### 2. Generate Documentation

**Method A: Command Line**
```bash
php generator.php
```

**Method B: Browser Access**
1. Upload `generator.php` to your web server
2. Open it in your browser
3. Documentation will be generated automatically in the `output/` subdirectory
4. View the result at `output/index.html`

### 3. View Documentation

Open `output/index.html` in your web browser.

## 🌐 Live Demo

- **Generator:** https://phpdg.com/demo/generator.php
- **Documentation:** https://phpdg.com/demo/output/

## 📖 Usage Example

### Input (PHP file with DocBlocks):
```php
<?php
/**
 * User authentication class
 */
class UserAuth {
    /**
     * Authenticate user credentials
     * 
     * @param string $username User's username
     * @param string $password User's password
     * @return bool Authentication result
     */
    public function login($username, $password) {
        // Authentication logic
        return true;
    }
}
```

### Output:

Beautiful HTML documentation with:
- Class overview
- Method signatures with source code viewer
- Parameter descriptions
- Return types
- Searchable interface

## 🔐 HTTP Authentication

To enable password protection:
```php
'http_auth' => [
    'admin' => 'secure_password',
    'user' => 'another_password',
],
```

The generator will automatically create `.htaccess` and `.htpasswd` files.

## 🌍 Supported Languages

The documentation interface supports 10 languages with a built-in language picker:

- 🇬🇧 **English (en)** - default
- 🇸🇰 **Slovak (sk)** - Slovenčina
- 🇨🇿 **Czech (cs)** - Čeština
- 🇩🇪 **German (de)** - Deutsch
- 🇵🇱 **Polish (pl)** - Polski
- 🇵🇹 **Portuguese (pt)** - Português
- 🇷🇺 **Russian (ru)** - Русский
- 🇺🇦 **Ukrainian (uk)** - Українська
- 🇮🇳 **Hindi (hi)** - हिन्दी
- 🇮🇷 **Persian (fa)** - فارسی (RTL support)

Change default language in settings: `'language' => 'en'`

Users can switch languages directly in the documentation interface using the language picker (saves preference to localStorage).

## ✨ What's New in v0.5.0

### Source Code Viewer
- Click "View Source" button to see the implementation of any method
- AJAX-powered modal window for smooth experience
- Shows exact line numbers from the original file

### Expanded Language Support
- Increased from 6 to 10 languages
- Added: Polish, Portuguese, Ukrainian, Hindi, Persian
- Full RTL (right-to-left) support for Persian

### Other Improvements
- Rebranding from phpDoc to phpdg
- Improved modal UI components
- Better handling of large codebases

## 📁 Project Structure
```
phpdg/
├── generator.php          # Main generator script
└── output/               # Generated documentation
    ├── index.html       # Main index
    ├── .htaccess        # Apache protection (optional)
    ├── .htpasswd        # HTTP authentication users (if enabled)
    └── ...              # Generated files
```

## 📝 License

MIT License

## 👨‍💻 Author

Created for developers who need quick and beautiful PHP documentation.

## 🐛 Issues & Contributions

Found a bug or have a feature request? Feel free to open an issue or submit a pull request!

---

**Version:** 0.5.0  
**Last Updated:** January 2024  
**Previous Version:** 0.4.7