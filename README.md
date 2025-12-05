# Lituus Foundation Website

The official website for Lituus Foundation — Guardians of Decentralized Truth.

## About

Lituus Foundation is building infrastructure for truth that doesn't require trust. We support the development of decentralized oracle systems and prediction markets through strategic resource allocation and community empowerment.

## Tech Stack

- **Framework**: [Astro 5.16.4](https://astro.build) - Static site generation with zero JS by default
- **Styling**: [Tailwind CSS 4](https://tailwindcss.com) - Utility-first CSS framework
- **Deployment**: [Cloudflare Workers](https://workers.cloudflare.com) - Edge-first deployment
- **Fonts**: Inter (sans-serif), Cormorant Garamond (serif)

## Getting Started

### Prerequisites

- Node.js 18+
- npm or pnpm

### Installation

```bash
# Clone the repository
git clone https://github.com/lituus-foundation/lituus-foundation-website.git
cd lituus-foundation-website

# Install dependencies
npm install
```

### Development

```bash
# Start development server at localhost:4321
npm run dev
```

### Build

```bash
# Build for production
npm run build

# Preview production build with Wrangler (Workers runtime)
npm run preview
```

### Deployment

```bash
# Deploy to Cloudflare Workers
npm run deploy

# Generate Cloudflare type definitions
npm run cf-typegen
```

## Project Structure

```
lituus-foundation-website/
├── public/              # Static assets
│   └── favicon.svg
├── src/
│   ├── components/      # Reusable Astro components
│   ├── layouts/         # Page layouts
│   ├── pages/           # File-based routing
│   ├── styles/          # Global styles
│   │   └── global.css
│   └── env.d.ts         # TypeScript definitions
├── astro.config.mjs     # Astro configuration
├── tailwind.config.js   # Tailwind configuration
├── tsconfig.json        # TypeScript configuration
└── wrangler.jsonc       # Cloudflare Workers configuration
```

## Design Features

- **Glassmorphism UI**: Subtle glass-panel effects with backdrop blur
- **Animated Components**:
  - Parallax scrolling hero section
  - Rotating coil background animation
  - Icon micro-interactions on hover
- **Responsive Design**: Mobile-first approach with breakpoint optimization
- **Accessibility**:
  - Semantic HTML
  - ARIA labels
  - Reduced motion support
  - Keyboard navigation

## Configuration

### Cloudflare Workers

The project is configured for edge deployment via Cloudflare Workers:

- Static assets served via Workers Assets binding
- Image optimization through Cloudflare Image Service
- Platform proxy enabled for local development

### TypeScript

Strict mode enabled with full type safety across the codebase.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

[MIT License](LICENSE)

## Links

- **Website**: [lituus.foundation](https://lituus.foundation)
- **Augur**: [augur.net](https://augur.net)
- **Twitter**: [@LituusDAO](https://twitter.com/LituusDAO)
- **Discord**: [Join our community](https://discord.gg/lituus)
- **Telegram**: [Lituus Foundation](https://t.me/lituusfoundation)

---

Built with ♾️ by the Lituus Foundation team
