---
title: Configuration Guide
description: Detailed configuration options for Docsar
author: Docsar Team
date: 2024-01-15
tags: ["configuration", "setup"]
---

# Configuration Guide

Learn how to configure Docsar to perfectly fit your documentation needs.

## 📁 Configuration File

Docsar stores its configuration in `data/config.json`. Here's a complete example:

```json
{
  "repository": {
    "url": "https://github.com/username/docs-repo",
    "branch": "main",
    "private": true,
    "token": "ghp_xxxxxxxxxxxxxxxxxxxx"
  },
  "site": {
    "title": "My Project Documentation",
    "description": "Comprehensive documentation for my awesome project",
    "logo": "https://example.com/logo.png",
    "baseUrl": "https://docs.myproject.com"
  },
  "theme": {
    "name": "default",
    "custom": false,
    "path": "themes/custom"
  },
  "content": {
    "path": "docs",
    "defaultPage": "README.md"
  },
  "update": {
    "method": "webhook",
    "interval": 30,
    "webhookSecret": "my-secure-secret"
  }
}
```

## 🔧 Configuration Options

### Repository Settings

| Option | Type | Description | Example |
|--------|------|-------------|---------|
| `url` | string | Git repository URL | `https://github.com/user/repo` |
| `branch` | string | Branch to sync from | `main`, `master`, `docs` |
| `private` | boolean | Whether repository is private | `true`, `false` |
| `token` | string | Access token for private repos | `ghp_xxxxx` |

### Site Settings

| Option | Type | Description | Example |
|--------|------|-------------|---------|
| `title` | string | Site title | `My Documentation` |
| `description` | string | Site description | `Project documentation` |
| `logo` | string | Logo URL or path | `logo.png` |
| `baseUrl` | string | Site base URL | `https://docs.example.com` |

### Theme Settings

| Option | Type | Description | Example |
|--------|------|-------------|---------|
| `name` | string | Theme name | `default`, `dark`, `custom` |
| `custom` | boolean | Use custom theme | `true`, `false` |
| `path` | string | Custom theme path | `themes/mytheme` |

### Content Settings

| Option | Type | Description | Example |
|--------|------|-------------|---------|
| `path` | string | Documentation folder in repo | `docs`, `documentation` |
| `defaultPage` | string | Default/homepage file | `README.md`, `index.md` |

### Update Settings

| Option | Type | Description | Example |
|--------|------|-------------|---------|
| `method` | string | Update method | `manual`, `webhook`, `interval` |
| `interval` | number | Update interval in minutes | `30`, `60`, `1440` |
| `webhookSecret` | string | Webhook security secret | `my-secret-key` |

## 🎨 Theme Configuration

### Built-in Themes

Docsar comes with several built-in themes:

- **Default**: Clean, minimalistic design
- **Dark**: Dark mode optimized
- **Blue**: Blue accent colors
- **Green**: Green accent colors

### Custom Themes

You can create custom themes by:

1. Creating a `themes/` folder in your documentation repository
2. Adding CSS files with your custom styles
3. Configuring the theme path in settings

Example custom theme structure:
```
docs/
├── themes/
│   └── mytheme/
│       ├── style.css
│       ├── variables.css
│       └── components.css
└── README.md
```

## 🔄 Update Methods

### Manual Updates

The simplest method - updates when you click the refresh button:

```json
{
  "update": {
    "method": "manual"
  }
}
```

### Webhook Updates

Automatic updates when you push to your repository:

```json
{
  "update": {
    "method": "webhook",
    "webhookSecret": "optional-secret-for-security"
  }
}
```

#### Setting up GitHub Webhooks

1. Go to your repository Settings → Webhooks
2. Click "Add webhook"
3. Set Payload URL: `https://your-domain.com/api/webhook`
4. Content type: `application/json`
5. Secret: Your webhook secret (optional but recommended)
6. Select "Just the push event"

### Interval Updates

Periodic updates at specified intervals:

```json
{
  "update": {
    "method": "interval",
    "interval": 60
  }
}
```

## 🔐 Security Considerations

### Access Tokens

- Use tokens with minimal required permissions
- Regularly rotate access tokens
- Store tokens securely (they're masked in the UI)

### Webhook Secrets

- Always use webhook secrets in production
- Use strong, randomly generated secrets
- Keep secrets confidential

### File Permissions

Ensure proper file permissions:
- Configuration directory: `755`
- Configuration file: `600`
- Repository cache: `755`

## 🌍 Environment Variables

You can override configuration with environment variables:

| Variable | Description | Example |
|----------|-------------|---------|
| `NUXT_PUBLIC_SITE_URL` | Site base URL | `https://docs.example.com` |
| `NODE_ENV` | Environment | `production`, `development` |

## 📂 Directory Structure

Docsar uses this directory structure:

```
data/
├── config.json          # Main configuration
├── repo/                # Cloned repository cache
│   └── docs/            # Your documentation files
└── themes/              # Custom themes (if any)
```

## 🔧 Advanced Configuration

### Custom Markdown Processing

You can customize how Markdown is processed by modifying the parser settings in your theme files.

### Logo Configuration

Logos can be:
- **External URLs**: `https://example.com/logo.png`
- **Repository files**: `logo.png` (relative to repo root)
- **Base64 encoded**: `data:image/png;base64,iVBOR...`

### Multi-language Support

Organize your documentation for multiple languages:

```
docs/
├── en/
│   ├── README.md
│   └── guides/
├── de/
│   ├── README.md
│   └── guides/
└── fr/
    ├── README.md
    └── guides/
```

## 🚨 Troubleshooting Configuration

### Configuration Not Loading

1. Check file permissions on `data/config.json`
2. Verify JSON syntax is valid
3. Ensure all required fields are present

### Repository Access Issues

1. Verify repository URL is correct
2. Check access token permissions
3. Test repository access manually

### Theme Not Applying

1. Verify theme path is correct
2. Check CSS file syntax
3. Clear browser cache

## 📝 Configuration Best Practices

1. **Backup your configuration** regularly
2. **Use version control** for custom themes
3. **Test configuration changes** in development first
4. **Monitor update logs** for issues
5. **Keep access tokens secure** and rotated

## 🎯 Next Steps

- [Learn basic usage](../guides/basic-usage.md)
- [Set up advanced features](../guides/advanced-features.md)
- [Explore the API](../api/overview.md)
- [Troubleshoot issues](../troubleshooting/common-issues.md)