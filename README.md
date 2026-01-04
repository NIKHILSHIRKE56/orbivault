# Orbivault Website

A modern, responsive website for Orbivault - a certificate outage prevention product.

## Features

- **8 Pages**: Home, Product, How It Works, Pricing, Security, Docs, Demo Dashboard, Contact
- **Fully Responsive**: Works seamlessly on mobile, tablet, and desktop
- **Interactive Demo**: Frontend-only demo dashboard with mock data and optional real API integration
- **Modern Design**: Clean, professional SaaS-style interface with security/devops aesthetic
- **Contact Form**: Lead collection with client-side validation and success notifications

## Tech Stack

- React 18
- TypeScript
- Vite
- Tailwind CSS
- React Router DOM
- Lucide React (icons)

## Getting Started

### Prerequisites

- Node.js 16+ and npm

### Installation

```bash
# Install dependencies
npm install
```

### Development

```bash
# Start development server
npm run dev
```

The site will be available at `http://localhost:5173`

### Build

```bash
# Build for production
npm run build
```

The built files will be in the `dist/` directory.

### Preview Production Build

```bash
# Preview the production build locally
npm run preview
```

## Project Structure

```
src/
├── components/
│   ├── Navbar.tsx       # Main navigation bar
│   ├── Footer.tsx       # Site footer
│   └── Badge.tsx        # Risk level badge component
├── pages/
│   ├── Home.tsx         # Landing page
│   ├── Product.tsx      # Product features page
│   ├── HowItWorks.tsx   # How it works page
│   ├── Pricing.tsx      # Pricing plans
│   ├── Security.tsx     # Security & compliance
│   ├── Docs.tsx         # Documentation with API examples
│   ├── Demo.tsx         # Interactive demo dashboard
│   └── Contact.tsx      # Contact form
├── App.tsx              # Router configuration
├── main.tsx             # Application entry point
└── index.css            # Global styles (Tailwind)
```

## Demo Dashboard

The demo page (`/demo`) includes:

- **Mock Data Mode** (default): Uses predefined certificate data for demonstration
- **Real API Mode**: Toggle to connect to `http://localhost:8000/scan/batch` endpoint
- **Batch Scanning**: Enter multiple domains (one per line) to scan
- **Results Table**: View certificate details with risk indicators

### Using Real API

To use the real API mode:

1. Ensure you have the Orbivault backend running on `http://localhost:8000`
2. Navigate to `/demo`
3. Toggle "Use Real API" in the sidebar
4. Enter domains and click "Run Scan"

### Changing API Base URL

To change the API endpoint, edit the fetch URL in `src/pages/Demo.tsx`:

```typescript
const response = await fetch('http://localhost:8000/scan/batch', {
  // ... change URL here
});
```

## Deployment

### Static Site Deployment

The built site is completely static and can be deployed to any static hosting service:

#### Netlify

```bash
# Install Netlify CLI
npm install -g netlify-cli

# Build and deploy
npm run build
netlify deploy --prod --dir=dist
```

#### Vercel

```bash
# Install Vercel CLI
npm install -g vercel

# Build and deploy
npm run build
vercel --prod
```

#### GitHub Pages

```bash
# Build the project
npm run build

# Deploy the dist/ folder to gh-pages branch
```

#### Any Static Host

Simply upload the contents of the `dist/` folder to your web server.

### Environment Configuration

For production deployments with a real API:

1. Update the API URL in `src/pages/Demo.tsx`
2. Configure CORS on your backend to allow requests from your domain
3. Rebuild the project

## Design System

### Colors

- **Primary**: Blue (#2563eb)
- **Success**: Green (#10b981)
- **Warning**: Yellow (#f59e0b)
- **Error**: Red (#ef4444)
- **Neutral**: Gray scale

### Risk Badges

- **OK**: Green (30+ days until expiry)
- **WARN**: Yellow (15-30 days)
- **CRITICAL**: Orange (<15 days)
- **EXPIRED**: Red (already expired)
- **UNKNOWN**: Gray (status unknown)

### Typography

- **Headings**: Bold, using default font stack
- **Body**: Regular weight, optimized line height
- **Code**: Monospace font for code blocks

## Customization

### Updating Brand Colors

Edit `tailwind.config.js` to customize the color palette.

### Modifying Page Content

All page content is contained in the respective files in `src/pages/`. Simply edit the JSX and text content.

### Adding New Pages

1. Create a new component in `src/pages/`
2. Add a route in `src/App.tsx`
3. Add navigation link in `src/components/Navbar.tsx`

## Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## License

All rights reserved.

## Contact

- Email: hello@orbivault.io
- Website: https://orbivault.io
