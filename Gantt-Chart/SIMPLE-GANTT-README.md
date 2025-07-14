# Simple Program Project Gantt Chart

## 🎯 Overview
Clean, simplified Gantt chart focusing on Program → Project hierarchy with timeline bars calculated from G0/G5 dates and status colors applied directly to the bars.

## ✨ Key Features

### **Timeline Bars**
- **Calculated from G0/G5 dates**: Timeline bars automatically calculated from start/end dates
- **Status colors on bars**: Project status colors applied directly to timeline bars
- **No separate status column**: Status is visually represented in the timeline

### **Program Grouping**
- **Program colors**: Each program has unique color for visual grouping
- **Sorted by program**: Projects grouped under their respective programs
- **Visual hierarchy**: Clear program-project relationship

### **Clean Design**
- **No filters**: Simplified interface without dropdown filters
- **Today line**: Red dashed line showing current date
- **Tooltips**: Hover for project details
- **Professional styling**: Clean, corporate appearance

## 📋 Data Structure

### Required Columns
| Column | Type | Description |
|--------|------|-------------|
| `program` | Text | Program name |
| `project` | Text | Project name within program |
| `projectManager` | Text | Project manager name |
| `g0Date` | Date (DD/MM/YYYY) | Project start date |
| `g5Date` | Date (DD/MM/YYYY) | Project end date |
| `projectStatus` | Text | Status: "On Track", "At Risk", "Delayed", "Completed", "Not Started" |

## 🎨 Visual Design

### **Status Colors (Applied to Timeline Bars)**
- **On Track**: Green (#27ae60)
- **At Risk**: Orange (#f39c12)
- **Delayed**: Red (#e74c3c)
- **Completed**: Blue (#3498db)
- **Not Started**: Gray (#95a5a6)

### **Program Colors**
- Each program gets a unique color from the category palette
- Helps visually group projects under programs

### **Layout**
- **Left side**: Program, Project, Manager, G0 Date, G5 Date columns
- **Right side**: Timeline bars with status colors
- **Today line**: Red dashed line across the chart

## 🔧 Power BI Implementation

### Step 1: Install Deneb Visual
1. Open Power BI Desktop
2. Go to **Visualizations** pane
3. Click **Get more visuals**
4. Search for "Deneb" and install

### Step 2: Prepare Your Data
1. Import data with required columns
2. Ensure date format: DD/MM/YYYY
3. Verify status values match exactly

### Step 3: Create the Visual
1. Add Deneb visual to your report
2. Map fields to Deneb visual:
   - Program → Program
   - Project → Project
   - Project Manager → ProjectManager
   - G0 Date → G0Date
   - G5 Date → G5Date
   - Project Status → ProjectStatus

### Step 4: Configure Vega Spec
1. Click **Edit** in Deneb visual
2. Paste contents of `Simple-Gantt-Chart.json`
3. Click **Apply**

## 🎯 Key Features

### **Timeline Visualization**
- **Gantt bars**: Calculated from G0 to G5 dates
- **Status colors**: Applied directly to timeline bars
- **Duration**: Automatically calculated and displayed
- **Overlaps**: Shows project overlaps clearly

### **Program Grouping**
- **Color coding**: Each program has unique color
- **Visual grouping**: Projects under same program grouped together
- **Easy scanning**: Quickly identify program boundaries

### **Interactive Elements**
- **Hover tooltips**: Rich project information
- **Today indicator**: Red dashed line for current date
- **Clean interface**: No clutter, focus on timeline

## 📊 Tooltip Information

Hovering over timeline bars shows:
- **Project Name**
- **Program**
- **Project Manager**
- **G0 Date** (Start)
- **G5 Date** (End)
- **Duration** (in days)
- **Status**

## ⚙️ Configuration Options

### **Visual Settings**
```json
{
  "showTooltips": true,
  "showTodayLine": true,
  "textColour": "#2c3e50",
  "backgroundColor": "#ffffff",
  "yRowHeight": 45
}
```

### **Column Widths**
```json
{
  "programColumnWidth": 180,
  "projectColumnWidth": 200,
  "managerColumnWidth": 120,
  "g0DateColumnWidth": 90,
  "g5DateColumnWidth": 90
}
```

## 🚀 Performance Tips

### **Optimization**
- Works well with 20-100 projects
- Efficient timeline calculations
- Clean rendering without complex interactions

### **Data Best Practices**
- Consistent program naming
- Valid date ranges (G5 > G0)
- Proper status values
- Complete project information

## 🔍 Troubleshooting

### **Common Issues**
1. **Timeline not showing**: Check G0/G5 date format (DD/MM/YYYY)
2. **Status colors wrong**: Verify exact status text values
3. **Programs not grouping**: Ensure consistent program names
4. **Performance slow**: Reduce number of projects

### **Data Validation**
- All required columns present
- Valid date formats
- Correct status values
- Program hierarchy consistency

## 📈 Use Cases

### **Program Management**
- Visualize program timelines
- Track project progress within programs
- Identify program bottlenecks

### **Project Oversight**
- Monitor project timelines
- Status tracking and reporting
- Manager accountability

### **Executive Reporting**
- High-level program view
- Status summaries
- Timeline overviews

## 🎨 Customization Examples

### **Change Status Colors**
```json
"color": {
  "type": "ordinal",
  "domain": ["On Track", "At Risk", "Delayed", "Completed", "Not Started"],
  "range": ["#00ff00", "#ffff00", "#ff0000", "#0000ff", "#cccccc"]
}
```

### **Adjust Layout**
```json
{
  "yRowHeight": 50,
  "programColumnWidth": 200,
  "projectColumnWidth": 250
}
```

## 📞 Support

For implementation issues:
1. Check data format and column mapping
2. Verify Power BI Deneb version
3. Test with sample data first
4. Review error messages in Deneb editor

---

**Version**: 1.0 Simple  
**Last Updated**: 2024  
**Compatibility**: Power BI Deneb Visual 