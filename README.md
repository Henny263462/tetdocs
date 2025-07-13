# Docsar Documentation Platform

Welcome to **Docsar** - a modern, minimalistic documentation platform that automatically syncs with your Git repositories to provide beautiful, searchable documentation from your Markdown files.

## 🚀 Quick Start

Getting started with Docsar is simple:

1. **Configure your repository** through the setup wizard
2. **Push your documentation** to your Git repository
3. **Access your docs** through the beautiful web interface

## ✨ Features

- **Git Integration**: Automatically sync with any Git repository
- **Markdown Support**: Full support for GitHub Flavored Markdown
- **Syntax Highlighting**: Beautiful code blocks with language detection
- **Dark/Light Themes**: Switch between themes seamlessly
- **Responsive Design**: Works perfectly on all devices
- **Auto-navigation**: Generates sidebar from your folder structure
- **Webhook Support**: Auto-update when you push changes

## 📖 Documentation Structure

Your documentation should be organized in a clear folder structure:

```
docs/
├── README.md
├── getting-started/
│   ├── installation.md
│   ├── configuration.md
│   └── first-steps.md
├── guides/
│   ├── basic-usage.md
│   ├── advanced-features.md
│   └── best-practices.md
├── api/
│   ├── overview.md
│   ├── authentication.md
│   └── endpoints.md
└── troubleshooting/
    ├── common-issues.md
    └── faq.md
```

## 🎨 Markdown Features

Docsar supports all standard Markdown features plus some enhancements:

### Code Blocks

\`\`\`javascript
function greet(name) {
  console.log(`Hello, ${name}!`);
}

greet('Docsar');
\`\`\`

### Tables

| Feature | Status | Description |
|---------|--------|-------------|
| Git Sync | ✅ | Automatic repository synchronization |
| Themes | ✅ | Dark and light mode support |
| Search | 🚧 | Coming soon |
| Comments | 📋 | Planned |

### Alerts

> **Note**: This is an informational note about important details.

> **Warning**: This is a warning about potential issues.

> **Tip**: This is a helpful tip for better usage.

## 🔧 Configuration

Docsar can be configured through the web interface or by manually editing the `config.json` file:

```json
{
  "repository": {
    "url": "https://github.com/username/docs",
    "branch": "main",
    "private": false
  },
  "site": {
    "title": "My Documentation",
    "description": "Documentation for my awesome project"
  },
  "update": {
    "method": "webhook"
  }
}
```

## 🔗 Next Steps

Ready to dive deeper? Check out these guides:

- [Installation Guide](getting-started/installation.md) - Set up Docsar
- [Configuration](getting-started/configuration.md) - Configure your site
- [Basic Usage](guides/basic-usage.md) - Learn the basics
- [API Reference](api/overview.md) - Explore the API

---

**Happy documenting!** 📝