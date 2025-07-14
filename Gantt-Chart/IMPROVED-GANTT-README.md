# Improved Portfolio Program Project Gantt Chart

## 🚀 Major Improvements Made

### **Critical Fixes Implemented:**
- ✅ **Tooltips**: Comprehensive project details on hover
- ✅ **Portfolio Dropdown Filter**: Clean hierarchy management
- ✅ **Status Legend**: Clear color coding explanation
- ✅ **Working Zoom Controls**: Days/Months/Years/All functionality
- ✅ **Proper Date Formatting**: DD/MM/YYYY format
- ✅ **Visual Hierarchy**: Program colors, better typography
- ✅ **Error Handling**: Null data handling
- ✅ **Interactive Feedback**: Hover states, cursor changes

### **New Features:**
- 🎯 **Portfolio Filter**: Dropdown to filter by portfolio
- 📊 **Status Legend**: Visual status indicator
- 🎨 **Program Color Coding**: Each program has unique color
- 📅 **Today Line**: Red dashed line showing current date
- 🔍 **Enhanced Tooltips**: Rich project information
- ⚡ **Performance Optimized**: Efficient signal handling

## 📋 Data Structure

### Required Columns
| Column | Type | Description |
|--------|------|-------------|
| `portfolio` | Text | Portfolio name (used for filtering) |
| `program` | Text | Program name within portfolio |
| `project` | Text | Project name within program |
| `projectManager` | Text | Project manager name |
| `g0Date` | Date (DD/MM/YYYY) | Project start date |
| `g5Date` | Date (DD/MM/YYYY) | Project end date |
| `prevG5Date` | Date (DD/MM/YYYY) | Previous G5 date (can be null) |
| `projectStatus` | Text | Status: "On Track", "At Risk", "Delayed", "Completed", "Not Started" |

## 🎨 Visual Design

### **Color Scheme**
- **On Track**: Green (#27ae60)
- **At Risk**: Orange (#f39c12)
- **Delayed**: Red (#e74c3c)
- **Completed**: Blue (#3498db)
- **Not Started**: Gray (#95a5a6)

### **Typography Hierarchy**
- **Headers**: 13px, Bold
- **Program Names**: 12px, Bold, Colored
- **Project Names**: 11px, Regular
- **Manager/Date**: 11px, Regular
- **Status**: 10px, Regular

### **Layout**
- **Filter Panel**: Top-left portfolio dropdown
- **Zoom Controls**: Top-center timeline zoom
- **Status Legend**: Top-right status indicators
- **Table**: Left side with project details
- **Gantt Chart**: Right side with timeline bars

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
2. Paste contents of `Portfolio-Gantt-Improved.json`
3. Click **Apply**

## 🎯 Key Features

### **Portfolio Filter**
- Dropdown in top-left corner
- Filter by specific portfolio or "All"
- Real-time filtering without page refresh

### **Timeline Zoom**
- **Days**: Detailed day-level view
- **Months**: Month-level overview
- **Years**: Year-level perspective
- **All**: Complete project timeline

### **Interactive Elements**
- **Hover**: Rich tooltips with project details
- **Click**: Select projects (for drill-through)
- **Double-click**: Reset zoom/pan
- **Mouse wheel**: Zoom in/out on timeline

### **Status Visualization**
- **Color-coded bars**: Project timeline bars
- **Status indicators**: Small colored squares
- **Legend**: Clear status explanation
- **Today line**: Red dashed line for current date

## 📊 Tooltip Information

Hovering over project bars shows:
- **Project Name**
- **Program**
- **Portfolio**
- **Project Manager**
- **G0 Date** (Start)
- **G5 Date** (End)
- **Previous G5 Date**
- **Duration** (in days)
- **Status**
- **Delay Information** (if applicable)

## ⚙️ Configuration Options

### **Visual Settings**
```json
{
  "showTooltips": true,
  "showButtons": true,
  "showStatusLegend": true,
  "showTodayLine": true,
  "textColour": "#2c3e50",
  "backgroundColor": "#ffffff",
  "yRowHeight": 45
}
```

### **Column Widths**
```json
{
  "programColumnWidth": 140,
  "projectColumnWidth": 180,
  "managerColumnWidth": 120,
  "g0DateColumnWidth": 90,
  "g5DateColumnWidth": 90,
  "prevG5DateColumnWidth": 90,
  "statusColumnWidth": 100
}
```

## 🚀 Performance Tips

### **Optimization**
- Limit to ~50-100 projects for best performance
- Use portfolio filters to reduce data load
- Consider date ranges for large datasets
- Use zoom levels to focus on relevant time periods

### **Data Best Practices**
- Consistent naming conventions
- Valid date ranges (G5 > G0)
- Proper status values
- Complete project information

## 🔍 Troubleshooting

### **Common Issues**
1. **Dates not displaying**: Check DD/MM/YYYY format
2. **Status colors wrong**: Verify exact status text
3. **Filter not working**: Ensure portfolio column is mapped
4. **Performance slow**: Reduce number of projects

### **Data Validation**
- All required columns present
- Valid date formats
- Correct status values
- Portfolio hierarchy consistency

## 📈 Use Cases

### **Portfolio Management**
- Track multiple portfolios simultaneously
- Filter focus on specific portfolios
- Monitor cross-portfolio dependencies

### **Program Oversight**
- Visualize program timelines
- Identify program bottlenecks
- Track program progress

### **Project Management**
- Detailed project timelines
- Status tracking and reporting
- Manager accountability

### **Executive Reporting**
- High-level portfolio view
- Status summaries
- Timeline overviews

## 🎨 Customization Examples

### **Change Color Scheme**
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
  "programColumnWidth": 150,
  "projectColumnWidth": 200
}
```

### **Modify Tooltips**
Edit the tooltip signal to show different information or format.

## 📞 Support

For implementation issues:
1. Check data format and column mapping
2. Verify Power BI Deneb version
3. Test with sample data first
4. Review error messages in Deneb editor

For customization requests:
1. Modify signals in the spec
2. Adjust visual properties
3. Test changes incrementally
4. Validate with your data

---

**Version**: 2.0 Improved  
**Last Updated**: 2024  
**Compatibility**: Power BI Deneb Visual 