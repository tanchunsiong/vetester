# VETester - Virtual Earth Image Overlay

Web application demonstrating Bing Maps (Virtual Earth) image overlay technique. Displays custom georeferenced images on top of Bing Maps base layer with proper scaling and positioning based on zoom level.

Developed for Microsoft Popfly Competition (2008).

## Features

- Custom image overlay on Bing Maps
- Zoom-aware image scaling
- Geographic image positioning (lat/long anchoring)
- Opacity control for overlay transparency
- Dynamic image resize based on zoom level
- Hide/show overlay during zoom animation

## Tech Stack

- **Platform**: ASP.NET Web Application
- **API**: Virtual Earth JavaScript API v6.1
- **Languages**: JavaScript, HTML, CSS
- **Map Service**: Microsoft Virtual Earth (Bing Maps)

## Image Overlay Configuration

```javascript
var imageUpperLeftCornerLatitude = 1.474065;
var imageUpperLeftCornerLongitude = 104.121552;
var originalHeight = 3000;  // pixels
var originalWidth = 1800;   // pixels
```

### Default Location
Singapore region (Latitude: 1.474065, Longitude: 104.121552)

## How It Works

### Initialization
1. Load Virtual Earth map at specified location and zoom
2. Convert geographic coordinates to pixel coordinates
3. Position image element using absolute positioning
4. Append image to map layer container

### Zoom Handling
1. Hide image during zoom animation (performance optimization)
2. On zoom complete:
   - Calculate new image dimensions based on zoom level
   - Recalculate image position in pixel coordinates
   - Update image size and position
   - Show image (currently disabled - visibility remains hidden)

### Scaling Formula
```javascript
newWidth = originalWidth × 2^(currentZoom - imageZoomLevel)
newHeight = originalHeight × 2^(currentZoom - imageZoomLevel)
```

Image reference zoom level: 7

## Image URL

```
http://labs.innovativesingapore.com/smsgateway/finalimage.png
```

External PNG image with transparency support. Opacity set to 70% for blending with base map.

## Installation

1. Host on IIS or web server
2. Open `VETester.sln` in Visual Studio (optional)
3. Navigate to `VE.htm` in web browser
4. Ensure internet connection for Virtual Earth API

## Use Cases

- Weather radar overlays
- Custom map layers (traffic, events)
- Property boundary visualization
- Historical map comparisons
- Satellite image overlays
- Planning/zoning maps

## Configuration

To use custom image:

1. Replace image URL in `VE.htm`:
```javascript
<img src="YOUR_IMAGE_URL_HERE" id="overlay" />
```

2. Update geographic anchor point:
```javascript
var imageUpperLeftCornerLatitude = YOUR_LAT;
var imageUpperLeftCornerLongitude = YOUR_LONG;
```

3. Set original image dimensions:
```javascript
var originalHeight = YOUR_HEIGHT;
var originalWidth = YOUR_WIDTH;
```

4. Adjust reference zoom level (if needed):
```javascript
var imageZoomLevel = YOUR_ZOOM;
```

## Technologies

- **Virtual Earth JavaScript API v6.1**
- **VEMap** object for map control
- **VELatLong** for coordinate representation
- **LatLongToPixel()** for coordinate conversion
- Dynamic DOM manipulation
- CSS absolute positioning

## License

MIT License

## Links

- Blog post: [VETester: Georeferenced Image Overlays on Bing Maps](https://www.tanchunsiong.com/2008/11/vetester-georeferenced-image-overlays-on-bing-maps/)
- GitHub: [github.com/tanchunsiong](https://github.com/tanchunsiong)
- LinkedIn: [linkedin.com/in/tanchunsiong](https://linkedin.com/in/tanchunsiong)
- X: [x.com/tanchunsiong](https://x.com/tanchunsiong)

**Project Created:** 2008 (Popfly Competition / SP Year 3)
