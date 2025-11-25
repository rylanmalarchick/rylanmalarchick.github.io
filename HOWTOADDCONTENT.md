# How to Add Content

## Quick Reference for Adding New Posts/Projects

### Add a New Blog Post

1. Create a new file in `content/posts/`:
   ```bash
   ./hugo new content/posts/your-post-name.md
   ```

2. Or manually create `content/posts/your-post-name.md`:
   ```markdown
   ---
   title: "Your Post Title"
   date: 2025-11-24
   draft: false
   tags: ["Tag1", "Tag2", "Tag3"]
   summary: "A brief summary of your post"
   ---

   Your content here...
   ```

### Add a New Project

1. Create a new file in `content/projects/`:
   ```bash
   ./hugo new content/projects/your-project-name.md
   ```

2. Or manually create `content/projects/your-project-name.md`:
   ```markdown
   ---
   title: "Your Project Title"
   date: 2025-11-24
   draft: false
   tags: ["Tag1", "Tag2"]
   summary: "Brief project description"
   ---

   ## Overview
   Project details here...

   ## Links
   - [GitHub](https://github.com/username/repo)
   ```

### Draft vs Published

- `draft: true` - Only visible with `./hugo server -D` (local development)
- `draft: false` - Visible in production builds and deployed site

### Local Development

**Preview with drafts** (see everything including drafts):
```bash
export PATH="$PWD:$PATH"
./hugo server -D
```
Visit: http://localhost:1313

**Preview production build** (only published content):
```bash
./hugo server
```

### Building for Production

Build the site (what gets deployed):
```bash
./hugo --minify
```

Output goes to `public/` directory.

### Publishing Workflow

1. Write your content in `content/posts/` or `content/projects/`
2. Set `draft: false` when ready to publish
3. Commit and push to GitHub:
   ```bash
   git add .
   git commit -m "Add new post: [title]"
   git push origin main
   ```
4. GitHub Actions automatically builds and deploys

### File Structure

```
content/
├── about/
│   └── _index.md          # About page
├── posts/
│   ├── post-1.md          # Blog posts
│   └── post-2.md
└── projects/
    ├── _index.md          # Projects index
    └── project-1.md       # Individual projects
```

### Useful Front Matter Options

```yaml
---
title: "Post Title"
date: 2025-11-24
draft: false              # true = draft, false = published
tags: ["tag1", "tag2"]    # Categorize your content
summary: "Short description"
cover:
  image: "image.jpg"      # Optional cover image
  alt: "Alt text"
  caption: "Caption"
showToc: true            # Show table of contents
weight: 1                # Order in lists (lower = first)
---
```

### Tips

- Use descriptive filenames: `fpga-quantum-emulator.md` not `post1.md`
- Always include a summary for better previews
- Tags help with organization and discovery
- Date format: `YYYY-MM-DD`
- Preview locally before pushing to production
