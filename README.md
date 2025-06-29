# Shelter Justice Support Utility

## Overview

The **Shelter Justice Support Utility** is a web-based mapping tool built with [Anvil](https://anvil.works/) and [Mapbox GL JS](https://docs.mapbox.com/mapbox-gl-js/). It enables users—particularly individuals in need or those assisting underserved communities—to search for local shelter, food, and support services near San Jose, California.

## Key Features

- Interactive Mapbox map embedded in an Anvil web application.
- Draggable user location marker for setting a custom position.
- Address search functionality using Mapbox Geocoder.
- Display of predefined static markers representing shelters and support organizations.
- Automatic calculation and display of driving routes to the two nearest support locations.
- Service descriptions, addresses, and contact phone numbers are shown for selected locations.

## Coding Languages & Technologies

### Python
- The main application logic is written in Python using Anvil’s client-side and server-side framework.
- Handles user interaction events, Haversine distance calculations, and API calls.

### JavaScript
- Mapbox GL JS and Mapbox Geocoder, both JavaScript libraries, are used for map rendering and geocoding.
- Anvil’s `anvil.js` module bridges Python with the browser’s JavaScript environment to manipulate the DOM and integrate with Mapbox.

### Mapbox GL JS & Mapbox Directions API
- Used to render the map, geocode addresses, and generate road-based directions.
- Requests to the Directions API are sent using Python via Anvil’s `anvil.http.request()`.

### HTML
- Inline HTML snippets are used to style and label markers on the map.
- These are injected into the DOM using JavaScript through `anvil.js`.

## How It Works

1. **Map Initialization**: The map loads centered on San Jose, CA.
2. **User Marker**: A draggable marker allows the user to set or adjust their location.
3. **Search**: Users can search for addresses using Mapbox’s geocoding tool.
4. **Static Markers**: A list of shelters and services is hardcoded and shown on the map.
5. **Distance Calculation**:
   - Haversine formula is used to identify the two closest locations.
   - Mapbox Directions API is used to get accurate road-based distances.
6. **Route Drawing**: Two driving routes are drawn on the map, one as a solid line and the other as a dashed line.
7. **Information Display**: The closest services are listed with driving distance, descriptions, and contact information.
