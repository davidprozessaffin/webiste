# Bold Landing Page

A visually striking landing page built with React, Tailwind CSS, and Framer Motion, following the design principles outlined in CLAUDE.md.

## Features

- **Bold Aesthetic Design**: Unique gradient effects, custom fonts (Playfair Display + Karla), and distinctive visual style
- **Smooth Animations**: Framer Motion-powered scroll animations, staggered reveals, and micro-interactions
- **Responsive Layout**: Mobile-first design that works beautifully on all devices
- **Custom Tailwind Config**: Extended with brand colors, custom shadows, and unique utilities
- **Performance Optimized**: Vite for fast builds and optimal loading

## Design Principles

This project follows the frontend development guidelines from CLAUDE.md:

- ✅ Avoiding generic AI aesthetics (no Inter, no purple-on-white clichés)
- ✅ Bold, intentional design choices
- ✅ Custom typography with character
- ✅ High-impact motion at key moments
- ✅ Distinctive visual identity

## Tech Stack

- **React 19** - Modern React with hooks
- **Vite** - Fast build tool and dev server
- **Tailwind CSS 4** - Utility-first styling with custom extensions
- **Framer Motion 12** - Production-ready animations
- **Custom Fonts** - Playfair Display (display) + Karla (body)

## Getting Started

Install dependencies:

```bash
npm install
```

Run development server:

```bash
npm run dev
```

Build for production:

```bash
npm run build
```

Preview production build:

```bash
npm run preview
```

## Project Structure

```
.
├── src/
│   ├── App.jsx          # Main application component
│   ├── main.jsx         # React entry point
│   └── index.css        # Tailwind imports and custom styles
├── index.html           # HTML template with font imports
├── tailwind.config.js   # Custom Tailwind configuration
├── vite.config.js       # Vite configuration
└── package.json         # Dependencies and scripts
```

## Customization

### Colors

Edit `tailwind.config.js` to customize the brand color palette.

### Fonts

Change fonts in `index.html` (Google Fonts) and `tailwind.config.js` (font family).

### Animations

Modify animation variants in `src/App.jsx` to adjust timing and effects.

## License

ISC

---

Built following [CLAUDE.md](./CLAUDE.md) design principles.
