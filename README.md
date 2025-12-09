# Competition Immo

A professional dashboard application for managing and evaluating architecture competitions. Enables structured evaluation of building project variants across multiple sustainability criteria.

**Live Demo**: https://davras5.github.io/competition-immo/

<p align="center">
  <img src="assets/images/Preview1.jpg" width="90%"/>
</p>

<p align="center">
  <img src="assets/images/Preview2.jpg" width="45%" style="vertical-align: top;"/>
  <img src="assets/images/Preview3.jpg" width="45%" style="vertical-align: top;"/>
</p>

## Features

### Project Management
- Browse projects in grid, list, or interactive map view
- Project details with address, usage type, status, and team assignments
- Status tracking (Draft, Active, Completed) with progress indicators
- Milestone timeline with completion tracking
- Team and expert management
- Image gallery for project visualizations

### Variant Evaluation System
- Support for multiple architectural variants per project
- Integration with evaluation frameworks (SNAP, SNBS, Minergie-P, Minergie-ECO, LEED)
- Quantitative metrics (Kennwerte) and qualitative criteria (Kriterien)
- Visual progress tracking per theme

### Data Visualization & Filtering
- Interactive Mapbox map with color-coded project markers
- Full-text search across projects
- Filter by status and usage type
- Side-by-side variant comparison (up to 5 variants)

### Responsive Design
- Mobile navigation with hamburger menu
- Touch-friendly interface
- Responsive layouts for all view modes

## Tech Stack

| Technology | Purpose |
|------------|---------|
| HTML5 | Structure and semantic markup |
| CSS3 | Styling with design tokens (CSS custom properties) |
| Vanilla JavaScript | Custom state management, hash-based routing, component rendering |
| JSON | Data storage |
| Mapbox GL JS v3.3.0 | Interactive maps |
| Material Symbols | Icon library |
| Source Sans 3 | Typography |

**No build step required** - Runs directly in any browser with minimal dependencies.

## Getting Started

```bash
# Clone the repository
git clone https://github.com/davras5/competition-immo.git
cd competition-immo

# Start a local server
python3 -m http.server 8000

# Open http://localhost:8000 in your browser
```

## Project Structure

```
competition-immo/
├── index.html                # Landing page with hero, features, frameworks overview
├── frameworks.html           # Evaluation frameworks reference page
├── README.md                 # Project documentation
├── STYLE_GUIDE.md            # Comprehensive design system documentation
├── LICENSE                   # MIT license
│
├── app/
│   ├── index.html            # Main single-file application (~1700 lines)
│   ├── styles.css            # Application-specific styles
│   └── data.json             # Project data, variants, Mapbox config
│
├── styles/
│   ├── main.css              # Shared styles for public pages
│   └── tokens.css            # Design tokens (colors, spacing, typography)
│
└── assets/
    └── images/               # Project images and assets
```

## Architecture

### Application Design
- **Single-Page Application (SPA)** with hash-based routing
- **Custom state management** with pub/sub pattern
- **Functional component pattern** with direct DOM manipulation
- **No external JS dependencies** (except Mapbox GL)

### Key Components
- `AppHeader` - Top navigation with logo and user menu
- `MainSidebar` - Navigation sidebar (overview, evaluation, 3D, comparison)
- `GalleryView` - Main project browser with grid/list/map modes
- `ProjectOverviewView` - Project details, team, and timeline
- `EvaluationView` - Criteria assessment per variant
- `ComparisonView` - Side-by-side variant comparison

### Design System
The project follows a comprehensive design system documented in `STYLE_GUIDE.md`:
- **Color philosophy**: Slate palette for institutional feel, color earned through meaning
- **Accessibility**: WCAG 2.1 AA compliant
- **Design tokens**: Single source of truth in `tokens.css`

## Data Configuration

Project data is stored in `/app/data.json`:
- Mapbox API token
- Project list with coordinates and metadata
- Variant definitions with thumbnails
- Evaluation themes and criteria
- Team member assignments

## Accessibility

- WCAG 2.1 AA compliant color contrast
- Semantic HTML structure
- ARIA labels on interactive elements
- Keyboard navigation support
- Focus indicators
- Color + icon combinations (colorblind-safe)

## Browser Support

Modern browsers with ES6+ support:
- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## License

Licensed under [MIT](https://opensource.org/licenses/MIT)

---

*Sample data included for demonstration purposes. Target users: Federal/Municipal governments, construction firms, architects.*
