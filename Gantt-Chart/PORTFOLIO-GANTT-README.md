# Portfolio Program Project Gantt Chart

## Overview
Production-grade Gantt chart for portfolio management with hierarchical display of Portfolio → Program → Project relationships, including project management data (G0/G5 dates, project status, managers).

## Features

### Core Functionality
- **Hierarchical Display**: Portfolio → Program → Project structure
- **Project Management Data**: G0/G5 dates, previous G5 dates, project status
- **Interactive Controls**: Zoom (Days/Months/Years/All), pan, expand/collapse
- **Status Visualization**: Color-coded status indicators and bars
- **Today Line**: Red dashed line showing current date
- **Professional Styling**: Corporate color scheme, clean typography

### Status Categories
- **On Track** (Green): Projects proceeding as planned
- **At Risk** (Orange): Projects with potential delays
- **Delayed** (Red): Projects behind schedule
- **Completed** (Blue): Finished projects
- **Not Started** (Gray): Projects not yet initiated

## Data Structure

### Required Columns
| Column | Type | Description |
|--------|------|-------------|
| `portfolio` | Text | Portfolio name |
| `program` | Text | Program name within portfolio |
| `project` | Text | Project name within program |
| `projectManager` | Text | Project manager name |
| `g0Date` | Date (DD/MM/YYYY) | Project start date |
| `g5Date` | Date (DD/MM/YYYY) | Project end date |
| `prevG5Date` | Date (DD/MM/YYYY) | Previous G5 date (can be null) |
| `projectStatus` | Text | Status: "On Track", "At Risk", "Delayed", "Completed", "Not Started" |

### Sample Data
See `portfolio-sample-data.json` for complete example.

## Power BI Implementation

### Step 1: Install Deneb Visual
1. Open Power BI Desktop
2. Go to **Visualizations** pane
3. Click **Get more visuals**
4. Search for "Deneb" and install

### Step 2: Prepare Your Data
1. Import your data with the required columns
2. Ensure date columns are in DD/MM/YYYY format
3. Verify project status values match the expected categories

### Step 3: Create the Visual
1. Add Deneb visual to your report
2. Drag all required fields to the Deneb visual:
   - Portfolio → Portfolio
   - Program → Program  
   - Project → Project
   - Project Manager → ProjectManager
   - G0 Date → G0Date
   - G5 Date → G5Date
   - Previous G5 Date → PrevG5Date
   - Project Status → ProjectStatus

### Step 4: Configure Vega Spec
1. Click **Edit** in Deneb visual
2. Paste the contents of `Portfolio-Gantt-Spec.json`
3. Click **Apply**

### Step 5: Customize (Optional)
Modify the following signals in the spec:
- `showTooltips`: Enable/disable tooltips
- `showButtons`: Show/hide zoom buttons
- `showTodayLine`: Show/hide today indicator
- `textColour`: Main text color
- `statusColors`: Status color mapping
- `yRowHeight`: Row height in pixels

## Configuration Options

### Visual Settings
```json
{
  "showTooltips": true,
  "showButtons": true, 
  "showTodayLine": true,
  "textColour": "#2c3e50",
  "backgroundColor": "#ffffff",
  "yRowHeight": 40
}
```

### Status Colors
```json
{
  "On Track": "#27ae60",
  "At Risk": "#f39c12",
  "Delayed": "#e74c3c", 
  "Completed": "#3498db",
  "Not Started": "#95a5a6"
}
```

## Usage Tips

### Navigation
- **Mouse Wheel**: Zoom in/out on timeline
- **Click & Drag**: Pan across timeline
- **Double Click**: Reset view
- **Zoom Buttons**: Quick zoom to Days/Months/Years/All

### Data Best Practices
- Use consistent naming for portfolios/programs
- Ensure G5 dates are after G0 dates
- Set prevG5Date to null for new projects
- Use exact status text values

### Performance
- Limit to ~100 projects for optimal performance
- Use date filters to show relevant time periods
- Consider breaking large portfolios into separate visuals

## Troubleshooting

### Common Issues
1. **Dates not displaying**: Check date format (DD/MM/YYYY)
2. **Status colors wrong**: Verify exact status text values
3. **Visual not loading**: Ensure all required columns are mapped
4. **Performance slow**: Reduce number of projects or date range

### Data Validation
- All required columns must be present
- Date columns must be valid dates
- Project status must match expected values
- Portfolio/Program/Project hierarchy must be consistent

## Customization Examples

### Change Color Scheme
```json
"statusColors": {
  "On Track": "#00ff00",
  "At Risk": "#ffff00", 
  "Delayed": "#ff0000",
  "Completed": "#0000ff",
  "Not Started": "#cccccc"
}
```

### Adjust Layout
```json
"portfolioColumnWidth": 150,
"programColumnWidth": 150,
"projectColumnWidth": 200,
"yRowHeight": 50
```

## Support
For issues or customization requests, refer to the original Deneb documentation or contact your Power BI administrator. 