# SLUSD School Boundary Lookup

A web application that helps families find their neighborhood schools in the San Leandro Unified School District by entering their home address.

## Features

- **Address Search**: Enter any address to find your assigned schools
- **Interactive Map**: Visual display of school boundary polygons on Google Maps
- **School Information**: Details for elementary, middle, and high schools including:
  - School names, addresses, and websites
  - Grade levels served
  - Direct links to school enrollment

## How It Works

1. Enter your address in the search field
2. The application geocodes your address using Google Maps
3. Determines which school boundary polygon contains your location
4. Displays your assigned elementary, middle, and high schools
5. Provides enrollment links and school contact information

## School Coverage

The application covers all SLUSD elementary schools:
- Garfield Elementary
- Halkin Elementary  
- Jefferson Elementary
- Madison Elementary
- McKinley Elementary
- Monroe Elementary
- Roosevelt Elementary
- Washington Elementary

Plus middle schools (Bancroft, John Muir) and San Leandro High School.

## Technical Stack

- **Frontend**: Vanilla JavaScript, HTML5, CSS3
- **Maps**: Google Maps JavaScript API with Places autocomplete
- **Geometry**: KML polygon parsing using geoxml3 library
- **Styling**: Custom CSS with responsive design

## Setup

### Prerequisites
- Google Maps API key with the following APIs enabled:
  - Maps JavaScript API
  - Places API
  - Geocoding API

### Installation

1. Clone the repository:
```bash
git clone [repository-url]
cd slusd-school-lookup
```

2. Create a `config.js` file with your Google Maps API key:
```javascript
const CONFIG = {
    GOOGLE_MAPS_API_KEY: 'your-api-key-here'
};
```

3. Serve the files using a local web server:
```bash
# Using Python 3
python -m http.server 8000

# Using Node.js http-server
npx http-server

# Using PHP
php -S localhost:8000
```

4. Open `http://localhost:8000` in your browser

### File Structure

```
├── index.html              # Main application page
├── styles.css              # Application styling
├── config.js               # API configuration (create this)
├── geoxml3.js              # KML parsing library
├── v3_epoly.js             # Polygon geometry utilities
├── maps/                   # School boundary KML files
│   ├── bancroft.xml        # Bancroft Middle School boundaries
│   ├── garfield.xml        # Garfield Elementary boundaries
│   ├── halkin.xml          # Halkin Elementary boundaries
│   ├── jefferson.xml       # Jefferson Elementary boundaries
│   ├── madison.xml         # Madison Elementary boundaries
│   ├── mckinley.xml        # McKinley Elementary boundaries
│   ├── monroe.xml          # Monroe Elementary boundaries
│   ├── muir.xml            # John Muir Middle School boundaries
│   ├── roosevelt.xml       # Roosevelt Elementary boundaries
│   └── washington.xml      # Washington Elementary boundaries
└── slusd-logo-white-border-128x128.svg
```

## Configuration

### Environment Variables
Create a `config.js` file (ignored by git) with:
- `GOOGLE_MAPS_API_KEY`: Your Google Maps API key

### API Requirements
Your Google Maps API key needs access to:
- **Maps JavaScript API**: For map display
- **Places API**: For address autocomplete
- **Geocoding API**: For address to coordinates conversion

## Browser Support

- Modern browsers with JavaScript enabled
- Responsive design for mobile and desktop
- Graceful degradation for older browsers

## Accessibility Features

- Keyboard navigation support
- Screen reader compatible
- High contrast mode support
- Reduced motion preferences respected
- Semantic HTML markup

## Inter-District Transfers

For addresses outside SLUSD boundaries, the application provides information about the inter-district transfer process and links to enrollment resources.
