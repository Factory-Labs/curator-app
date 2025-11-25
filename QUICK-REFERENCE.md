# Quick Reference: New Design Style

Fast reference for implementing the new curator app design style.

---

## Color Palette

### Primary
```css
--purple-primary: #7c3aed;
--purple-hover:   #6d28d9;
--purple-light:   #ede9fe;
```

### Grays
```css
--background:     #fafafa;
--text-primary:   #1a1a1a;
--text-secondary: #666;
--border:         #e5e5e5;
```

### Status
```css
--success: #10b981;
--info:    #3b82f6;
--warning: #f59e0b;
--error:   #ef4444;
```

---

## Layout Structure

```html
<body>
    <div class="sidebar">
        <div class="sidebar-icon">☰</div>
        <div class="sidebar-icon active">◎</div>
        <div class="sidebar-icon">◇</div>
    </div>
    
    <div class="main-wrapper">
        <div class="header">
            <div class="header-content">
                <div class="header-left">
                    <h1>Title</h1>
                    <p class="header-subtitle">Subtitle</p>
                </div>
                <div class="header-right">
                    <div class="points-badge">
                        <div class="points-icon">△</div>
                        3000
                    </div>
                    <div class="user-avatar"></div>
                </div>
            </div>
        </div>
        
        <div class="container">
            <!-- Page content -->
        </div>
    </div>
</body>
```

---

## Essential CSS

### Sidebar
```css
.sidebar {
    position: fixed;
    left: 0;
    top: 0;
    width: 72px;
    height: 100vh;
    background: white;
    border-right: 1px solid #e5e5e5;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px 0;
    gap: 20px;
    z-index: 100;
}

.sidebar-icon {
    width: 40px;
    height: 40px;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: background 0.2s;
    color: #666;
    font-size: 20px;
}

.sidebar-icon:hover {
    background: #f5f5f5;
}

.sidebar-icon.active {
    background: #ede9fe;
    color: #7c3aed;
}

.main-wrapper {
    margin-left: 72px;
}
```

### Header
```css
.header {
    background: white;
    border-bottom: 1px solid #e5e5e5;
    padding: 20px 30px;
    position: sticky;
    top: 0;
    z-index: 99;
}

.header-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.header-right {
    display: flex;
    align-items: center;
    gap: 15px;
}

.points-badge {
    background: #ede9fe;
    color: #7c3aed;
    padding: 6px 12px;
    border-radius: 20px;
    font-size: 14px;
    font-weight: 600;
    display: flex;
    align-items: center;
    gap: 6px;
}

.points-icon {
    width: 16px;
    height: 16px;
    background: #7c3aed;
    border-radius: 50%;
}

.user-avatar {
    width: 36px;
    height: 36px;
    border-radius: 50%;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}
```

### Cards
```css
.card {
    background: white;
    border: 1px solid #e5e5e5;
    border-radius: 12px;
    padding: 20px;
    transition: all 0.2s;
}

.card:hover {
    border-color: #7c3aed;
    box-shadow: 0 4px 12px rgba(124, 58, 237, 0.1);
}
```

### Buttons
```css
.btn-primary {
    background: #7c3aed;
    color: white;
    border: none;
    padding: 10px 18px;
    border-radius: 8px;
    font-size: 13px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s;
}

.btn-primary:hover {
    background: #6d28d9;
}

.btn-secondary {
    background: #f5f5f5;
    color: #666;
    border: 1px solid #e5e5e5;
    padding: 10px 18px;
    border-radius: 8px;
    font-size: 13px;
    font-weight: 600;
    cursor: pointer;
}
```

### Form Inputs
```css
.form-input {
    width: 100%;
    padding: 10px 12px;
    border: 1px solid #e5e5e5;
    border-radius: 8px;
    font-size: 13px;
    font-family: inherit;
    background: white;
    transition: border-color 0.2s;
}

.form-input:focus {
    outline: none;
    border-color: #7c3aed;
}
```

---

## Key Values

| Property | Value |
|----------|-------|
| Sidebar width | `72px` |
| Border width | `1px` |
| Card radius | `12px` |
| Button radius | `8px` |
| Input radius | `8px` |
| Primary purple | `#7c3aed` |
| Background | `#fafafa` |
| Border color | `#e5e5e5` |
| Text color | `#1a1a1a` |

---

## Find & Replace

When updating old files:

```
background: #f5f5f5       → background: #fafafa
border: 2px solid #e0e0e0 → border: 1px solid #e5e5e5
background: #10b981       → background: #7c3aed
color: #333               → color: #1a1a1a
border-radius: 8px        → border-radius: 12px (on cards)
```

---

## Spacing Scale

Based on 4px grid:

```
4px   - Tiny gap
8px   - Small gap
12px  - Medium gap
16px  - Large gap
20px  - XL gap
24px  - XXL gap
30px  - Container padding
```

---

## Typography

```css
/* Page Title */
h1 {
    font-size: 24px;
    font-weight: 700;
    color: #1a1a1a;
}

/* Section Title */
h2 {
    font-size: 18px;
    font-weight: 600;
    color: #1a1a1a;
}

/* Body Text */
p {
    font-size: 13px;
    color: #1a1a1a;
    line-height: 1.6;
}

/* Secondary Text */
.text-secondary {
    font-size: 13px;
    color: #666;
}
```

---

## Badges

```css
.badge-low {
    background: #d1fae5;
    color: #065f46;
}

.badge-medium {
    background: #dbeafe;
    color: #1e40af;
}

.badge-high {
    background: #fce7f3;
    color: #9f1239;
}
```

---

## Checklist for New Pages

When creating a new page:

- [ ] Add sidebar HTML
- [ ] Wrap content in .main-wrapper
- [ ] Use new header structure
- [ ] Apply purple primary color
- [ ] Use 1px borders (#e5e5e5)
- [ ] Use 12px radius on cards
- [ ] Use #fafafa background
- [ ] Use #1a1a1a text color
- [ ] Add purple hover states
- [ ] Include points badge in header
- [ ] Include user avatar in header

---

## Common Mistakes to Avoid

❌ Using 2px borders  
❌ Using green (#10b981) for primary  
❌ Using #333 for text  
❌ Forgetting sidebar margin  
❌ Missing points badge  
❌ Using 8px radius on cards  
❌ Gray hover shadows  
❌ Blue focus borders  

✅ Use 1px borders  
✅ Use purple (#7c3aed) for primary  
✅ Use #1a1a1a for text  
✅ Add 72px margin-left  
✅ Include points badge  
✅ Use 12px radius on cards  
✅ Purple-tinted shadows  
✅ Purple focus borders  

---

## Browser Support

- Chrome/Edge: ✅ Full support
- Firefox: ✅ Full support  
- Safari: ✅ Full support
- IE11: ❌ Not supported

---

Quick reference complete! 🎨
