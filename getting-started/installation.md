---
title: Installation Guide
description: How to install and set up Docsar documentation platform
author: Docsar Team
date: 2024-01-15
tags: ["installation", "setup", "getting-started"]
---

# Installation Guide

This guide will walk you through installing and setting up Docsar for your documentation needs.

## 📋 Prerequisites

Before installing Docsar, make sure you have:

- **Node.js** 18 or higher
- **Git** for repository management
- A **Git repository** containing your documentation
- **Docker** (optional, for production deployment)

## 🛠️ Installation Methods

### Method 1: Development Setup

Perfect for local development and testing:

```bash
# Clone the Docsar repository
git clone https://github.com/your-org/docsar.git
cd docsar

# Install dependencies
npm install

# Start development server
npm run dev
```

The development server will start at `http://localhost:3000`.

### Method 2: Docker Deployment

Recommended for production environments:

```bash
# Using Docker Compose (recommended)
docker-compose up -d

# Or build and run manually
docker build -t docsar .
docker run -p 3000:3000 -v docsar_data:/app/data docsar
```

### Method 3: Build for Production

For custom deployments:

```bash
# Build the application
npm run build

# Start production server
npm run preview
```

## 🔧 Initial Configuration

When you first access Docsar, you'll be greeted with a setup wizard:

### Step 1: Repository Configuration

Configure your documentation repository:

- **Repository URL**: Your Git repository URL
- **Branch**: The branch to sync from (usually `main`)
- **Private Repository**: Enable if your repo is private
- **Access Token**: Required for private repositories

### Step 2: Site Configuration

Set up your site details:

- **Site Title**: The name of your documentation site
- **Description**: A brief description of your project
- **Default Page**: The landing page (usually `README.md`)

### Step 3: Update Configuration

Choose how Docsar should update your documentation:

- **Manual**: Update manually via the refresh button
- **Webhook**: Automatic updates via GitHub webhooks
- **Interval**: Periodic updates (specify interval in minutes)

### Step 4: Review and Complete

Review your configuration and complete the setup.

## 🔐 Setting Up Private Repositories

For private repositories, you'll need to create a personal access token:

### GitHub Personal Access Token

1. Go to GitHub Settings → Developer settings → Personal access tokens
2. Click "Generate new token (classic)"
3. Select the `repo` scope for full repository access
4. Copy the generated token
5. Use this token in the Docsar setup wizard

### GitLab Access Token

1. Go to GitLab User Settings → Access Tokens
2. Create a new token with `read_repository` scope
3. Copy the generated token
4. Use this token in the Docsar setup wizard

## 🌐 Production Deployment

### Environment Variables

Set these environment variables for production:

```bash
NODE_ENV=production
NUXT_PUBLIC_SITE_URL=https://your-domain.com
```

### Reverse Proxy Setup

Example Nginx configuration:

```nginx
server {
    listen 80;
    server_name your-domain.com;

    location / {
        proxy_pass http://localhost:3000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_cache_bypass $http_upgrade;
    }
}
```

## 📂 Data Persistence

Docsar stores configuration and repository data in the `/app/data` directory. Make sure to:

- Mount this directory as a volume in Docker
- Backup this directory regularly
- Set appropriate permissions (writable by the application)

## ✅ Verification

After installation, verify everything is working:

1. **Access the setup wizard** at your configured URL
2. **Complete the configuration** with your repository details
3. **Check that documentation loads** correctly
4. **Test the update mechanism** you configured
5. **Verify theme switching** works properly

## 🚨 Troubleshooting

### Common Issues

**Setup wizard doesn't appear:**
- Check that no `config.json` exists in the data directory
- Verify file permissions
- Check server logs for errors

**Repository clone fails:**
- Verify repository URL is correct
- Check access token permissions
- Ensure network connectivity to Git provider

**Updates not working:**
- Verify webhook URL is accessible
- Check webhook secret matches configuration
- Verify repository permissions

### Getting Help

If you encounter issues:

1. Check the [Troubleshooting Guide](../troubleshooting/common-issues.md)
2. Review the [FAQ](../troubleshooting/faq.md)
3. Check server logs for error messages
4. Verify your configuration settings

## 🎉 Next Steps

Now that Docsar is installed:

- [Configure your site](configuration.md)
- [Learn basic usage](../guides/basic-usage.md)
- [Set up webhooks](../guides/webhook-setup.md)
- [Explore advanced features](../guides/advanced-features.md)

Happy documenting! 📚