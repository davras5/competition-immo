# Competition Immo

A dashboard for managing and evaluating architecture competitions. Enables structured evaluation of building project variants across multiple sustainability criteria.

- Demo: https://davras5.github.io/competition-immo/

## Features

- Browse and manage construction project competitions
- Compare architectural variants side-by-side
- Interactive map with project locations
- Multi-dimensional evaluation across 4 themes: Functionality, Comfort & Health, Economics, Resources & Energy
- Progress tracking with milestones and team management
- Full-text search across projects
- Filter by status and usage type
- Grid, list, and map view modes
- Edit mode for project data management
- Image gallery for project visualizations
- Mobile-responsive design

## Tech Stack

| Technology | Purpose |
|------------|---------|
| HTML5 | Structure and semantic markup |
| CSS3 | Styling with CSS custom properties (design tokens) |
| Vanilla JavaScript | Custom state management, hash-based routing, dynamic UI |
| JSON | Data storage |
| Mapbox GL JS | Interactive maps |
| Material Symbols | Icon library |

**Minimal dependencies** - No build step required, runs directly in any browser.

## Getting Started

```bash
# Clone the repository
git clone https://github.com/davras5/competition-immo.git
cd competition-immo

# Start a local server
python3 -m http.server 8000

# Open http://localhost:8000
```

## Project Structure

```
competition-immo/
├── index.html              # Single-file web application
├── data.json               # Project and variant data
└── LICENSE                 # MIT license
```

## License

Licensed under [MIT](https://opensource.org/licenses/MIT)

---

*Sample data included for demonstration purposes.*
