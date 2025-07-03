# Hike Webapp Prompt

## Original User Request

> read sketch.jpeg in this directory. I want you to use it as a guide to code a webapp for all the best hikes in Ireland. Use Leaflet.js for the interactive map. I want a sleek, minimal, dark mode interface using only black and white. The output should be one self contained HTML file

## Sketch Analysis

The sketch showed:
- Layout with scrollable list on the left 
- Interactive map on the right
- Collapsible dropdowns for each hike
- Ability to mark hikes as done
- Clean, minimal interface design

## Implementation Requirements

### Core Features
- **Scrollable sidebar** with hike list and collapsible dropdown details
- **Interactive Leaflet.js map** with location markers
- **Minimal dark mode** styling using only black and white colors
- **Self-contained HTML file** with all dependencies via CDN
- **Mark as completed** functionality with visual feedback
- **Mobile responsive** design with sidebar toggle

### Technical Stack
- HTML5 with semantic structure
- CSS3 with flexbox layout and dark theme
- Leaflet.js for interactive mapping
- Vanilla JavaScript for interactivity
- No external dependencies beyond Leaflet CDN

### Design Specifications
- **Color scheme**: Pure black (#000) and white (#fff) only
- **Typography**: System fonts (-apple-system, BlinkMacSystemFont, etc.)
- **Layout**: Sidebar (400px) + map container (flex: 1)
- **Mobile**: Collapsible sidebar with hamburger toggle
- **Interactions**: Smooth transitions, hover effects, click handlers

### Data Structure
Each hike should include:
- `name`: Hike trail name
- `location`: Geographic area/park
- `coordinates`: [latitude, longitude] for map markers
- `difficulty`: Easy/Moderate/Challenging
- `distance`: Total distance (e.g., "12km")
- `duration`: Estimated time (e.g., "6-8 hours")
- `elevation`: Peak height or elevation gain
- `description`: Detailed trail description
- `completed`: Boolean for completion status

### Map Integration
- Center map on target region (Ireland: [53.4129, -8.2439], Victoria: [-37.0201, 144.9646])
- Use dark tile layer from CartoDB
- Custom markers that change appearance when completed
- Click markers to expand corresponding sidebar item
- Pan to location when sidebar item expanded

### Interaction Features
- Collapsible hike details with smooth animations
- Checkbox to mark hikes as completed
- Strikethrough text and opacity changes for completed items
- Map marker updates when completion status changes
- Mobile-friendly touch interactions

## Reusable for Any Region

This prompt template can be adapted for any hiking region by:
1. Changing the map center coordinates
2. Updating the title and description
3. Replacing the hike data array with region-specific trails
4. Adjusting zoom level as needed for geographic area

## Example Usage

```javascript
// Ireland center
const map = L.map('map').setView([53.4129, -8.2439], 7);

// Victoria, Australia center  
const map = L.map('map').setView([-37.0201, 144.9646], 7);
```