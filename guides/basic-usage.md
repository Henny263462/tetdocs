---
title: Basic Usage Guide
description: Learn the fundamentals of using Docsar
author: Docsar Team
date: 2024-01-15
tags: ["guide", "basics", "usage"]
---

# Basic Usage Guide

This guide covers the essential features and workflows of Docsar to help you get the most out of your documentation platform.

## 📝 Writing Documentation

### Markdown Basics

Docsar uses **GitHub Flavored Markdown** with additional enhancements. Here are the key formatting options:

#### Headers

```markdown
# H1 - Page Title
## H2 - Section
### H3 - Subsection
#### H4 - Sub-subsection
```

#### Text Formatting

```markdown
**Bold text**
*Italic text*
~~Strikethrough~~
`Inline code`
```

#### Links and Images

```markdown
[Link text](https://example.com)
![Alt text](image.png "Optional title")
```

#### Lists

```markdown
- Unordered list item
- Another item
  - Nested item

1. Ordered list item
2. Another item
   1. Nested item
```

### Code Blocks

Docsar provides excellent syntax highlighting for code blocks:

```javascript
// JavaScript example
function calculateTotal(items) {
  return items.reduce((sum, item) => sum + item.price, 0);
}

const total = calculateTotal([
  { name: 'Item 1', price: 10 },
  { name: 'Item 2', price: 25 }
]);
```

```python
# Python example
def calculate_total(items):
    return sum(item['price'] for item in items)

items = [
    {'name': 'Item 1', 'price': 10},
    {'name': 'Item 2', 'price': 25}
]
total = calculate_total(items)
```

```bash
# Bash commands
npm install docsar
docker run -p 3000:3000 docsar
git clone https://github.com/user/docs.git
```

### Tables

Create beautiful tables with proper alignment:

| Feature | Status | Priority | Notes |
|---------|:------:|:--------:|-------|
| Git Sync | ✅ | High | Automatic synchronization |
| Themes | ✅ | Medium | Light/dark mode support |
| Search | 🚧 | High | Coming in v2.0 |
| Comments | 📋 | Low | Future feature |

### Frontmatter

Add metadata to your pages using YAML frontmatter:

```yaml
---
title: "Page Title"
description: "Page description for SEO"
author: "Author Name"
date: "2024-01-15"
tags: ["tag1", "tag2", "tag3"]
category: "guides"
published: true
---
```

## 🗂️ Organizing Content

### File Structure

Organize your documentation logically:

```
docs/
├── README.md              # Homepage
├── getting-started/       # Getting started guides
│   ├── installation.md
│   ├── configuration.md
│   └── first-steps.md
├── guides/               # User guides
│   ├── basic-usage.md
│   ├── advanced-features.md
│   └── best-practices.md
├── api/                  # API documentation
│   ├── overview.md
│   ├── authentication.md
│   └── endpoints/
│       ├── users.md
│       └── projects.md
├── examples/             # Code examples
│   ├── javascript.md
│   └── python.md
└── troubleshooting/      # Help and support
    ├── common-issues.md
    └── faq.md
```

### Navigation

Docsar automatically generates navigation based on your folder structure:

- **Folders** become collapsible sections
- **Files** become navigation items
- **README.md** files are prioritized
- **Alphabetical ordering** within each level

### Naming Conventions

Follow these conventions for better organization:

- Use **lowercase** with **hyphens** for file names
- Start with **numbers** for ordered content: `01-introduction.md`
- Use **descriptive names**: `user-authentication.md` not `auth.md`
- Keep folder names **short** but **descriptive**

## 🎨 Customizing Appearance

### Themes

Switch between light and dark themes using the theme toggle in the header.

### Custom Styling

Add custom CSS by creating theme files in your repository:

```css
/* themes/custom/style.css */
:root {
  --primary-color: #3b82f6;
  --secondary-color: #64748b;
}

.custom-highlight {
  background: linear-gradient(120deg, #a8e6cf 0%, #dcedc8 100%);
  padding: 1rem;
  border-radius: 0.5rem;
  margin: 1rem 0;
}
```

### Logo and Branding

Add your logo by:

1. **Repository file**: Place `logo.png` in your repository root
2. **External URL**: Configure in settings
3. **Base64**: Embed directly in configuration

## 🔄 Updating Content

### Manual Updates

Click the refresh button in the header to manually update your documentation.

### Automatic Updates

Set up webhooks for automatic updates:

1. **GitHub**: Repository Settings → Webhooks
2. **Payload URL**: `https://your-domain.com/api/webhook`
3. **Content type**: `application/json`
4. **Events**: Just the push event

### Version Control

Best practices for managing documentation versions:

- Use **feature branches** for major changes
- **Tag releases** for version-specific docs
- **Review changes** before merging
- **Test updates** in development first

## 🔍 Content Best Practices

### Writing Tips

1. **Start with an overview** - Explain what the page covers
2. **Use clear headings** - Structure content hierarchically
3. **Include examples** - Show, don't just tell
4. **Add navigation** - Link between related pages
5. **Keep it current** - Regularly update outdated information

### SEO Optimization

- Use **descriptive titles** in frontmatter
- Add **meta descriptions** for each page
- Include **relevant tags** and categories
- Create **internal links** between pages
- Use **semantic HTML** structure

### Accessibility

- Use **descriptive link text** instead of "click here"
- Add **alt text** for all images
- Ensure **good color contrast** in custom themes
- Structure content with **proper headings**
- Test with **screen readers** when possible

## 📱 Mobile Experience

Docsar is fully responsive and optimized for mobile devices:

- **Collapsible sidebar** on small screens
- **Touch-friendly** navigation
- **Readable text** on all screen sizes
- **Fast loading** on mobile networks

## 🔧 Advanced Features

### Cross-References

Link between documentation pages:

```markdown
See the [Installation Guide](../getting-started/installation.md) for setup instructions.

Check out our [API Reference](../api/overview.md) for detailed endpoint documentation.
```

### Embedding Content

Embed external content:

```markdown
<!-- YouTube videos -->
[![Video Title](https://img.youtube.com/vi/VIDEO_ID/0.jpg)](https://www.youtube.com/watch?v=VIDEO_ID)

<!-- Code from external files -->
```typescript
// This could be pulled from a repository file
interface User {
  id: string;
  name: string;
  email: string;
}
```

### Interactive Elements

Add interactive elements to your documentation:

```markdown
> **💡 Tip**: This is a helpful tip for users.

> **⚠️ Warning**: This highlights important warnings.

> **📝 Note**: Additional information that's good to know.
```

## 🎯 Next Steps

Now that you understand the basics:

- [Explore advanced features](advanced-features.md)
- [Learn about webhook setup](webhook-setup.md)
- [Check out API documentation](../api/overview.md)
- [Read best practices](best-practices.md)

## 💬 Getting Help

If you need assistance:

- Check the [FAQ](../troubleshooting/faq.md)
- Review [common issues](../troubleshooting/common-issues.md)
- Contact support through your configured channels

Happy documenting! 🚀