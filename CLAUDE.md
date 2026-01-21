# CLAUDE.md - Frontend Development Guide

## Purpose
This file guides Claude in building exceptional marketing/landing pages with React + Tailwind CSS. It ensures every build has bold, distinctive aesthetics that avoid generic AI patterns.

## Quick Start Checklist
Before starting any frontend work:
- [ ] What's the aesthetic direction? (Choose ONE bold direction)
- [ ] What makes this design UNFORGETTABLE?
- [ ] What fonts will create character? (Avoid Inter, Roboto, Arial)
- [ ] What's the color story beyond standard gradients?
- [ ] How will motion enhance key moments?

---

## Frontend Development Philosophy

### Core Principle
**Choose a BOLD aesthetic direction and execute it with precision.** Both refined minimalism and bold maximalism work—the key is intentionality, not intensity.

### Design Thinking Process
Before writing any code, understand:

1. **Purpose**: What problem does this interface solve? Who uses it?

2. **Aesthetic Tone** - Pick ONE and commit fully:
   - Brutally minimal
   - Maximalist chaos
   - Retro-futuristic
   - Organic/natural
   - Luxury/refined
   - Playful/toy-like
   - Editorial/magazine
   - Brutalist/raw
   - Art deco/geometric
   - Soft/pastel
   - Industrial/utilitarian

3. **Differentiation**: What's the ONE thing someone will remember about this design?

### ❌ What NOT to Do

**Never use generic AI aesthetics:**
- ❌ Overused fonts: Inter, Roboto, Arial, system fonts, Space Grotesk
- ❌ Cliche color schemes (especially purple gradients on white)
- ❌ Predictable layouts and component patterns
- ❌ Cookie-cutter designs lacking context-specific character
- ❌ Repeated visual choices across different projects

**Instead:**
- ✅ Interpret creatively and make unexpected choices
- ✅ Ensure no two designs look the same
- ✅ Vary between light/dark themes, different fonts, different aesthetics
- ✅ Choose beautiful, unique, interesting fonts

---

## Design Implementation Standards

### Code Requirements
Every implementation must be:
- ✅ Production-grade and functional
- ✅ Visually striking and memorable
- ✅ Cohesive with a clear aesthetic point-of-view
- ✅ Meticulously refined in every detail

### 1. Typography
**Priority: Typography is CRITICAL**
- Choose fonts that are beautiful, unique, and interesting
- Pair a distinctive display font with a refined body font
- Use `@import` or `next/font` for Google Fonts, or Adobe Fonts for premium options
- Avoid: Arial, Inter, Roboto, San Francisco, system-ui

**Examples of interesting fonts:**
- Display: Playfair Display, Cormorant, Epilogue, Cabinet Grotesk, Syne, Clash Display
- Body: Karla, Source Serif Pro, DM Sans, General Sans, Synonym

### 2. Color & Theme
- Commit to a cohesive aesthetic
- Use Tailwind's color system but EXTEND with custom colors
- Dominant colors with sharp accents > evenly-distributed timid palettes
- Create atmosphere, not just flat backgrounds

**Tailwind Config Example:**
```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        brand: {
          50: '#...',
          // ... custom palette
        },
      },
      fontFamily: {
        display: ['Playfair Display', 'serif'],
        body: ['Karla', 'sans-serif'],
      },
    },
  },
}
```

### 3. Motion & Animation
**Use Framer Motion for React animations**

Install: `npm install framer-motion`

**Principles:**
- High-impact moments > scattered effects
- Well-orchestrated page loads with staggered reveals
- Scroll-triggered animations for landing pages
- Surprise hover states
- Smooth, purposeful transitions

**Framer Motion Patterns:**
```jsx
import { motion } from 'framer-motion';

// Staggered children
const container = {
  hidden: { opacity: 0 },
  show: {
    opacity: 1,
    transition: {
      staggerChildren: 0.1
    }
  }
};

const item = {
  hidden: { opacity: 0, y: 20 },
  show: { opacity: 1, y: 0 }
};

// Scroll-triggered
<motion.div
  initial={{ opacity: 0 }}
  whileInView={{ opacity: 1 }}
  viewport={{ once: true }}
>
```

### 4. Spatial Composition
- Unexpected layouts (break the grid!)
- Asymmetry and overlap
- Diagonal flow
- Grid-breaking elements
- Generous negative space OR controlled density

**Tailwind Tools:**
- Use `grid` with custom `grid-template-columns`
- Absolute positioning for overlays
- Negative margins for overlapping elements
- `aspect-ratio` utilities for consistency

### 5. Backgrounds & Visual Details
Create atmosphere and depth:
- Gradient meshes (`bg-gradient-to-br`)
- Noise textures (SVG patterns or CSS filters)
- Geometric patterns (Tailwind + custom CSS)
- Layered transparencies (`bg-opacity-*`)
- Dramatic shadows (`shadow-2xl`, custom shadows)
- Decorative borders (`border-*`, `ring-*`)
- Grain overlays (CSS `::before` with background-image)

**Custom Tailwind Additions:**
```js
// Add to tailwind.config.js
boxShadow: {
  'brutal': '8px 8px 0px 0px rgba(0,0,0,1)',
  'glow': '0 0 20px rgba(255,255,255,0.5)',
}
```

---

## Technical Stack & Tools

### Core Technologies
- **Framework**: React (function components, hooks)
- **Styling**: Tailwind CSS with extensive customization
- **Animation**: Framer Motion
- **Build Tool**: Vite or Next.js (user preference)

### Font Resources
- [Google Fonts](https://fonts.google.com/) - Free, extensive library
- [Adobe Fonts](https://fonts.adobe.com/) - Premium, requires Adobe account
- [Fontshare](https://www.fontshare.com/) - Free, high-quality fonts
- [Fontsource](https://fontsource.org/) - Self-hosted npm packages

### Combining Tailwind with Custom CSS
When Tailwind isn't enough:
```jsx
// In component
<div className="relative overflow-hidden">
  <style jsx>{`
    .custom-gradient {
      background: radial-gradient(circle at 30% 50%, #ff00ff 0%, transparent 50%),
                  radial-gradient(circle at 70% 50%, #00ffff 0%, transparent 50%);
    }
  `}</style>
  <div className="custom-gradient h-screen" />
</div>
```

Or use Tailwind's arbitrary values:
```jsx
<div className="bg-[radial-gradient(circle_at_30%_50%,#ff00ff_0%,transparent_50%)]" />
```

---

## Landing Page Best Practices

### Hero Section Patterns
**Bold, conversion-focused heroes:**
- Large, unexpected typography (96px+)
- Animated entrance (staggered reveal)
- Clear, compelling CTA
- Visual anchor (illustration, photo, or abstract element)
- Scroll indicator for engagement

**Example Structure:**
```jsx
<motion.section
  className="h-screen flex items-center justify-center relative"
  initial="hidden"
  animate="show"
  variants={containerVariants}
>
  <motion.h1 variants={itemVariants} className="text-9xl font-display">
    Unforgettable Headline
  </motion.h1>
  <motion.p variants={itemVariants} className="text-2xl">
    Compelling subheadline
  </motion.p>
  <motion.button variants={itemVariants}>
    Strong CTA
  </motion.button>
</motion.section>
```

### Scroll-Triggered Animations
```jsx
<motion.div
  initial={{ opacity: 0, y: 50 }}
  whileInView={{ opacity: 1, y: 0 }}
  viewport={{ once: true, amount: 0.3 }}
  transition={{ duration: 0.6 }}
>
  Content that animates in on scroll
</motion.div>
```

### Call-to-Action Optimization
- High contrast with surrounding content
- Action-oriented copy ("Start Building" > "Learn More")
- Micro-interactions on hover
- Multiple CTAs at different scroll depths
- Clear value proposition near CTA

### Social Proof & Testimonials
- Animated testimonial carousels
- Logo clouds with subtle motion
- Statistics with count-up animations
- Case study previews

### Responsive Design
**Mobile-first approach:**
```jsx
// Tailwind breakpoints
<div className="text-4xl md:text-6xl lg:text-9xl">
  Responsive headline
</div>
```

**Test on:**
- Mobile (375px, 414px)
- Tablet (768px, 1024px)
- Desktop (1440px, 1920px)

### Performance Optimization
- Lazy load images: `loading="lazy"`
- Use Next.js Image component for automatic optimization
- Code-split heavy components
- Preload critical fonts
- Minimize animation on reduced-motion preference:

```jsx
// Respect user preferences
const prefersReducedMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;

<motion.div
  animate={prefersReducedMotion ? { opacity: 1 } : { opacity: 1, y: 0 }}
>
```

---

## GitHub Integration via MCP

### What is GitHub MCP?
The GitHub MCP (Model Context Protocol) server enables Claude to interact directly with GitHub repositories for reading code, managing issues/PRs, and monitoring CI/CD.

### Setup Options

#### Option 1: Remote Server (Recommended for VS Code 1.101+)
1. Install MCP-compatible host (VS Code, Claude Desktop, Cursor)
2. Use one-click install if available in VS Code
3. Authenticate via OAuth or Personal Access Token (PAT)

#### Option 2: Local Docker Setup
```json
// Add to MCP configuration
{
  "mcpServers": {
    "github": {
      "command": "docker",
      "args": [
        "run", "-i", "--rm",
        "-e", "GITHUB_PERSONAL_ACCESS_TOKEN",
        "ghcr.io/github/github-mcp-server"
      ],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "${input:github_token}"
      }
    }
  }
}
```

### Creating a Personal Access Token (PAT)
1. Go to GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Generate new token with scopes:
   - `repo` (full control of private repositories)
   - `read:packages` (download packages)
   - `read:org` (read org and team membership)
3. Copy token and store securely in environment variable

**Security Best Practices:**
- ❌ Never hardcode tokens in config files
- ✅ Use environment variables
- ✅ Set restrictive file permissions on config files
- ✅ Use separate tokens for different projects
- ✅ Rotate tokens periodically

### Available Toolsets
Configure which GitHub capabilities are available:

```bash
# Via command line
github-mcp-server --toolsets repos,issues,pull_requests,actions

# Via environment variable
GITHUB_TOOLSETS="repos,issues,pull_requests,actions"
```

**Common toolsets:**
- `repos` - Browse code, search files, analyze commits
- `issues` - Create, update, manage issues
- `pull_requests` - Create and manage PRs
- `actions` - Monitor CI/CD runs, analyze build failures

### Important Limitations
**GitHub MCP is primarily for:**
- ✅ Reading repository code
- ✅ Managing issues and PRs
- ✅ Monitoring GitHub Actions
- ✅ Analyzing code and commits

**NOT for direct repository writes:**
- ❌ Pushing code directly
- Use traditional git commands via Bash tool for commits/pushes

### GitHub Enterprise Support
For enterprise deployments:
```json
{
  "env": {
    "GITHUB_HOST": "https://your-enterprise-domain.com",
    "GITHUB_PERSONAL_ACCESS_TOKEN": "${input:token}"
  }
}
```

---

## Development Workflow

### Starting a New Feature
1. **Clarify Requirements**
   - What's the purpose?
   - Who's the audience?
   - What's the desired aesthetic tone?

2. **Design Exploration**
   - Choose bold aesthetic direction
   - Select fonts and color palette
   - Sketch layout and composition ideas
   - Plan key animations and interactions

3. **Implementation**
   - Set up component structure
   - Implement layout with Tailwind
   - Add typography and colors
   - Integrate Framer Motion animations
   - Refine details and micro-interactions

4. **Review & Refine**
   - Test responsive behavior
   - Verify accessibility (keyboard nav, screen readers)
   - Check performance (Lighthouse audit)
   - Polish animations and timing

### Git Workflow with Claude
**For committing code:**
```bash
# Check status
git status

# Stage changes
git add .

# Commit with descriptive message
git commit -m "Add hero section with staggered animation"

# Push to remote
git push origin main
```

**For creating pull requests:**
```bash
# Create new branch
git checkout -b feature/new-landing-page

# Make changes and commit
git add .
git commit -m "Implement new landing page design"

# Push branch
git push -u origin feature/new-landing-page

# Create PR (if GitHub CLI installed)
gh pr create --title "Add new landing page" --body "Description"
```

**Using GitHub MCP:**
- Ask Claude to read repository code
- Request analysis of issues or PRs
- Monitor GitHub Actions status
- Review Dependabot alerts

---

## Quick Reference

### Pre-Coding Questions
1. What aesthetic direction am I committing to?
2. What fonts will make this memorable?
3. Where will motion create impact?
4. What makes this design unforgettable?
5. Am I avoiding generic AI patterns?

### Tailwind + Framer Motion Starter

**Animated Hero Component:**
```jsx
import { motion } from 'framer-motion';

const containerVariants = {
  hidden: { opacity: 0 },
  show: {
    opacity: 1,
    transition: {
      staggerChildren: 0.2,
      delayChildren: 0.3,
    },
  },
};

const itemVariants = {
  hidden: { opacity: 0, y: 20 },
  show: { opacity: 1, y: 0 },
};

export default function Hero() {
  return (
    <motion.section
      className="min-h-screen flex flex-col items-center justify-center px-4 bg-gradient-to-br from-purple-900 to-indigo-900"
      initial="hidden"
      animate="show"
      variants={containerVariants}
    >
      <motion.h1
        className="text-6xl md:text-8xl lg:text-9xl font-display text-white mb-6"
        variants={itemVariants}
      >
        Bold Headline
      </motion.h1>
      <motion.p
        className="text-xl md:text-2xl text-purple-200 mb-8 max-w-2xl text-center"
        variants={itemVariants}
      >
        Compelling subheadline that describes value
      </motion.p>
      <motion.button
        className="px-8 py-4 bg-white text-purple-900 rounded-full font-bold text-lg hover:shadow-2xl transition-shadow"
        variants={itemVariants}
        whileHover={{ scale: 1.05 }}
        whileTap={{ scale: 0.95 }}
      >
        Get Started
      </motion.button>
    </motion.section>
  );
}
```

**Scroll-Triggered Section:**
```jsx
<motion.section
  className="py-20"
  initial={{ opacity: 0 }}
  whileInView={{ opacity: 1 }}
  viewport={{ once: true, amount: 0.3 }}
  transition={{ duration: 0.8 }}
>
  <h2>Section content</h2>
</motion.section>
```

**Staggered Grid:**
```jsx
const gridContainer = {
  hidden: { opacity: 0 },
  show: {
    opacity: 1,
    transition: {
      staggerChildren: 0.1,
    },
  },
};

const gridItem = {
  hidden: { opacity: 0, scale: 0.8 },
  show: { opacity: 1, scale: 1 },
};

<motion.div
  className="grid grid-cols-1 md:grid-cols-3 gap-8"
  variants={gridContainer}
  initial="hidden"
  whileInView="show"
  viewport={{ once: true }}
>
  {items.map((item, i) => (
    <motion.div key={i} variants={gridItem}>
      {item}
    </motion.div>
  ))}
</motion.div>
```

### Common Commands
```bash
# Install dependencies
npm install framer-motion

# Start dev server
npm run dev

# Build for production
npm run build

# Run linter
npm run lint

# Git operations
git status
git add .
git commit -m "message"
git push

# GitHub CLI (if installed)
gh pr create
gh issue list
gh repo view
```

---

## Notes for Future Development

### Extending This Guide
- Add project-specific design patterns as they emerge
- Document custom Tailwind utilities
- Include component library references
- Add performance benchmarks and goals

### Evolution
This file should grow with the project:
- New aesthetic explorations
- Successful animation patterns
- Reusable component snippets
- Lessons learned from previous builds

### Remember
**Claude is capable of extraordinary creative work. Don't hold back.** Show what can truly be created when thinking outside the box and committing fully to a distinctive vision.

---

*Last updated: 2026-01-21*
