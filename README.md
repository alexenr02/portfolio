# Portfolio Website Project

**Status:** Planning Complete - Ready for Implementation  
**Last Updated:** 2026-01-19

---

## Quick Links

### 📚 Documentation
- **[Documentation Index](docs/INDEX.md)** - Complete guide to all documentation
- **[Architecture Guide](docs/ARCHITECTURE.md)** - Technical architecture and implementation (2,465 lines)
- **[Progress Tracker](docs/PROGRESS_TRACKER.md)** - Current status, decisions, and next steps
- **[File Guide](docs/FILE_GUIDE.md)** - How to use the documentation
- **[Update Summary](docs/PLAN_UPDATE_SUMMARY.md)** - Architecture audit and updates

### 📄 Project
- **[License](LICENSE)** - Project license

---

## Project Overview

Building a high-performance portfolio website for an Embedded Systems & Software Engineer using modern web technologies with a focus on performance, accessibility, and maintainability.

### Key Features
- 🎨 Dark/Light theme with system preference detection
- 🚀 Optimized performance (Lighthouse 90+)
- ♿ WCAG AA accessibility compliant
- 📱 Mobile-first responsive design
- 🔒 Privacy-focused (GDPR compliant)
- 🎮 Interactive demos and experiments
- 📊 Server-side analytics (no cookies)

---

## Tech Stack

### Core
- **Astro 4.x** - Static site generator with islands architecture
- **Svelte 4.x** - Interactive components
- **Tailwind CSS 3.x** - Utility-first styling
- **TypeScript** - Type safety (strict mode)
- **MDX** - Content with components

### Enhancements
- **@threlte/core** - Three.js integration (Phase 4+)
- **GSAP** - Advanced animations
- **Lucide Svelte** - Icon library
- **Sentry** - Error tracking
- **Geist Fonts** - Typography (subsetted, variable)

### Deployment
- **Netlify** - Hosting and forms
- **GitHub** - Version control (GitHub Flow)

---

## Project Structure (Planned)

```
portfolio/
├── src/
│   ├── components/     # Svelte/Astro components
│   ├── content/        # MDX project content
│   ├── layouts/        # Page layouts
│   ├── pages/          # Route pages
│   ├── lib/            # Utilities and helpers
│   └── styles/         # Global styles and themes
├── public/             # Static assets
├── tests/              # Unit and E2E tests (Phase 7+)
└── netlify.toml        # Deployment configuration
```

---

## Development Phases

### Current Status: Phase 0 Preparation

| Phase | Status | Description |
|-------|--------|-------------|
| **Phase 0** | 🔵 Ready | Project setup and tooling |
| **Phase 1** | ⚪ Pending | Foundation and theme system |
| **Phase 2** | ⚪ Pending | Static sections (Hero, About, Skills, Contact) |
| **Phase 3** | ⚪ Pending | Projects section with filtering |
| **Phase 4** | ⚪ Pending | Interactive lab (measurement-first) |
| **Phase 5** | ⚪ Pending | Enhanced SEO and accessibility |
| **Phase 6** | ⚪ Pending | Performance optimization |
| **Phase 7** | ⚪ Pending | Testing (unit + E2E) |
| **Phase 8** | ⚪ Pending | Analytics and monitoring |
| **Phase 9** | ⚪ Pending | Documentation and deployment |
| **Phase 10** | ⚪ Future | Post-launch enhancements |

---

## Getting Started

### Prerequisites
- Node.js 20.x
- npm or pnpm
- Git

### Initial Setup (Phase 0)

```bash
# 1. Initialize Astro project
npm create astro@latest .

# 2. Install dependencies
npm install

# 3. Configure environment variables
cp .env.example .env
# Edit .env with your keys (Turnstile, Sentry)

# 4. Download and subset fonts
# Place in public/fonts/

# 5. Start development server
npm run dev
```

### Development Commands

```bash
npm run dev          # Start dev server
npm run build        # Build for production
npm run preview      # Preview production build
npm run lint         # Run ESLint
npm run format       # Format with Prettier
npm run test         # Run tests (Phase 7+)
```

---

## Key Decisions

### Simplified Git Workflow
**GitHub Flow** (not GitFlow)
- `main` branch deploys to production
- Feature branches for all changes
- Every PR gets Netlify deploy preview

### Performance-First Approach
- Deferred heavy features (Three.js, games) to Phase 4+
- Measure impact before adding features
- Bundle size budget: < 200KB initial, < 300KB total

### No PWA (Simplified)
- Simple manifest for "Add to Home Screen"
- No service worker complexity
- Easier maintenance

### Modern Browsers Only
- No IE11 support (EOL 2022)
- Smaller bundles, simpler code
- Focus on modern features

---

## Performance Targets

### Core Web Vitals
- **LCP:** < 2.5s
- **FID:** < 100ms
- **CLS:** < 0.1
- **INP:** < 200ms

### Lighthouse Scores
- **Performance:** 90+
- **Accessibility:** 100
- **Best Practices:** 90+
- **SEO:** 100

---

## Accessibility Commitment

This project prioritizes accessibility:
- ✅ WCAG AA compliance
- ✅ Semantic HTML
- ✅ Keyboard navigation
- ✅ Screen reader support
- ✅ Focus management
- ✅ Color contrast 4.5:1
- ✅ Reduced motion support
- ✅ High contrast mode support

---

## Privacy & Security

### Data Collection
- **Analytics:** Netlify (server-side, no cookies)
- **Forms:** Netlify Forms (100/month limit)
- **Errors:** Sentry (runtime monitoring)
- **CAPTCHA:** Cloudflare Turnstile

### Security Headers
- X-Frame-Options: DENY
- Content-Security-Policy (hardened)
- X-Content-Type-Options: nosniff
- And more (see netlify.toml)

### Privacy Policy
Comprehensive disclosure of all data collection (see `/privacy` page)

---

## Contact Information

**Email:** aelejandro9@proton.me  
**Form Submissions:** Via Netlify Forms (with fallback)  
**Spam Protection:** Honeypot + Cloudflare Turnstile

---

## Environment Variables

Required variables (see `.env.example`):

```bash
# Cloudflare Turnstile
PUBLIC_TURNSTILE_SITE_KEY=your_site_key

# Sentry Error Tracking
PUBLIC_SENTRY_DSN=your_dsn
SENTRY_AUTH_TOKEN=your_token
SENTRY_ORG=your_org
SENTRY_PROJECT=your_project
```

---

## Browser Support

```
> 0.5%
last 2 versions
not dead
Firefox ESR
iOS >= 12
Android >= 6
```

**Note:** IE11 not supported (significant bundle savings)

---

## Architecture Highlights

### Island Architecture
- 90% static HTML/CSS
- JavaScript only where needed
- Svelte components hydrate on demand

### Content Strategy
- MDX for projects with interactive elements
- Markdown for simple content
- Type-safe content collections with Zod

### Font Strategy
- Self-hosted Geist Sans + Geist Mono
- Variable fonts (fewer files)
- Subsetted (Latin + Latin Extended only)
- font-display: swap

### Image Strategy
- WebP format with automatic fallbacks
- Lazy loading below-the-fold
- Responsive images with srcset
- Dark mode borders/shadows

---

## Testing Strategy

### Phase 0-3: Manual + Linting
- ESLint + Prettier
- Manual browser testing
- Manual accessibility checks

### Phase 7: Unit Tests
- Vitest for utilities
- Component logic testing

### Phase 8: E2E Tests
- Playwright for critical flows
- Manual accessibility testing

### Phase 10: Automation (Post-Launch)
- Lighthouse CI (warnings only)
- Automated E2E for regressions
- Optional: @axe-core/playwright

---

## Maintenance Plan

### Dependency Updates
**Manual quarterly updates** (no automated bot)
- Review changelog before updating
- Test thoroughly after updates
- Update in batches, not individually

### Monitoring
- **Sentry:** Real-time error tracking
- **Netlify Analytics:** Traffic and performance
- **Lighthouse:** Manual performance audits

---

## Project Timeline

### Week 1-2: Setup & Foundation
- Phase 0: Project setup
- Phase 1: Base layout and theme

### Week 3-4: Core Content
- Phase 2: Static sections
- Phase 3: Projects section

### Week 5-6: Enhancement
- Phase 4: Interactive features (measured)
- Phase 5: SEO and accessibility

### Week 7: Polish & Testing
- Phase 6: Performance optimization
- Phase 7: Testing

### Week 8: Launch
- Phase 8: Analytics setup
- Phase 9: Deployment

---

## Success Criteria

### Technical
- ✅ Lighthouse Performance 90+
- ✅ Zero accessibility violations
- ✅ Fast load times (< 3.5s TTI)
- ✅ Mobile-responsive
- ✅ Cross-browser compatible

### User Experience
- ✅ Clear navigation
- ✅ Fast, smooth interactions
- ✅ Professional appearance
- ✅ Easy content updates

### Maintenance
- ✅ Clear code structure
- ✅ Documented components
- ✅ Easy to update
- ✅ Low maintenance overhead

---

## Resources

### Documentation
- [Astro Documentation](https://docs.astro.build)
- [Svelte Documentation](https://svelte.dev/docs)
- [Tailwind CSS](https://tailwindcss.com/docs)
- [WCAG Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)

### Tools
- [Lighthouse](https://developers.google.com/web/tools/lighthouse)
- [axe DevTools](https://www.deque.com/axe/devtools/)
- [WebPageTest](https://www.webpagetest.org/)

---

## Contributing

This is a personal portfolio project. However, feedback and suggestions are welcome!

---

## License

See [LICENSE](LICENSE) file for details.

---

**Ready to build!** See `PORTFOLIO_ARCHITECTURE_PLAN.md` for complete implementation details.
