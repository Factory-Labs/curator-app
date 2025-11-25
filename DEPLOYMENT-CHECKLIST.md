# Deployment Checklist

Use this checklist before deploying the updated mockups to GitHub Pages.

---

## Pre-Deployment Checks

### ✅ File Verification

- [ ] All 8 HTML files are in `/mnt/user-data/outputs/`
- [ ] All 3 documentation files are present
- [ ] README.md is present and complete
- [ ] No broken file references

### ✅ Visual Testing

Open each file in a browser and verify:

**bounty-applicant-selection.html**
- [ ] Sidebar visible on left
- [ ] Header has points badge and avatar
- [ ] Applicant cards have purple hover
- [ ] Selection counter works
- [ ] "Confirm Selection" button is purple

**create-hard-bounty-fixed.html**
- [ ] Sidebar visible on left
- [ ] Header has points badge and avatar
- [ ] Tier sliders display correctly
- [ ] Budget calculator shows purple accents
- [ ] Form inputs have thin borders
- [ ] "Create Bounty" button is purple

**create-low-bounty.html**
- [ ] Sidebar visible on left
- [ ] Header has points badge and avatar
- [ ] All form fields display correctly
- [ ] Character counters work
- [ ] Budget calculator shows correctly
- [ ] "Create Bounty" button is purple

**create-medium-bounty-no-ai.html**
- [ ] Sidebar visible on left
- [ ] Header has points badge and avatar
- [ ] Form fields all display correctly
- [ ] Dropdowns work properly
- [ ] "Create Bounty" button is purple

**create-medium-bounty-with-ai.html**
- [ ] Sidebar visible on left
- [ ] Header has points badge and avatar
- [ ] AI suggestion boxes display correctly
- [ ] All form fields work
- [ ] "Create Bounty" button is purple

**passing-pool-confirmation.html**
- [ ] Sidebar visible on left
- [ ] Header has points badge and avatar
- [ ] Stat cards display correctly
- [ ] Participant cards show properly
- [ ] "Finalize & Distribute" button is purple
- [ ] Chart displays (if any)

**index.html**
- [ ] Landing page displays correctly
- [ ] All cards show properly
- [ ] Links to other pages work
- [ ] Gradient background displays

**evaluations-tab.html**
- [ ] Reference styling is correct
- [ ] Sidebar displays properly
- [ ] Header layout is correct
- [ ] All components render well

### ✅ Interaction Testing

Test in each file:

- [ ] All buttons are clickable
- [ ] Hover states work (purple border/shadow)
- [ ] Focus states work (purple border)
- [ ] Form inputs accept text
- [ ] Dropdowns open/close
- [ ] Character counters update
- [ ] Calculations work (if any)

### ✅ Cross-Browser Testing

Test in multiple browsers:

- [ ] Chrome (latest)
- [ ] Firefox (latest)
- [ ] Safari (latest)
- [ ] Edge (latest)

### ✅ Responsive Testing

Test at different sizes:

- [ ] Desktop (1920x1080)
- [ ] Laptop (1366x768)
- [ ] Tablet (768x1024)
- [ ] Mobile (375x667)

Check that:
- [ ] Sidebar remains visible/collapses appropriately
- [ ] Content scales properly
- [ ] No horizontal scrolling (unless intended)
- [ ] Touch targets are adequate on mobile

---

## Deployment Steps

### Step 1: Prepare Repository

```bash
# Navigate to repository
cd /path/to/curator-app

# Ensure you're on the correct branch
git checkout main

# Pull latest changes
git pull origin main
```

### Step 2: Copy Files

```bash
# Copy HTML files
cp /mnt/user-data/outputs/*.html ./

# Copy documentation
cp /mnt/user-data/outputs/*.md ./docs/

# Or copy all at once
cp /mnt/user-data/outputs/* ./
```

### Step 3: Review Changes

```bash
# Check what changed
git status

# Review specific changes
git diff bounty-applicant-selection.html
```

### Step 4: Commit Changes

```bash
# Stage all updated files
git add *.html *.md

# Commit with descriptive message
git commit -m "Update curator app mockups to new design style

- Add fixed 72px sidebar to all pages
- Update color scheme to purple primary (#7c3aed)
- Change borders to 1px with lighter color (#e5e5e5)
- Update card radius to 12px
- Add points badge and user avatar to headers
- Apply purple-tinted hover effects
- Include comprehensive documentation

All files tested and verified across browsers."
```

### Step 5: Push to GitHub

```bash
# Push to main branch
git push origin main
```

### Step 6: Verify GitHub Pages

1. Navigate to repository settings
2. Ensure GitHub Pages is enabled
3. Check source is set to `main` branch
4. Wait 1-2 minutes for deployment
5. Visit: `https://factory-labs.github.io/curator-app/`

### Step 7: Test Live Site

- [ ] Visit live URL
- [ ] Check index.html loads
- [ ] Navigate between pages
- [ ] Verify all links work
- [ ] Test on mobile device
- [ ] Check browser console for errors

---

## Post-Deployment Verification

### ✅ Functionality Check

- [ ] All pages accessible via URL
- [ ] Navigation between pages works
- [ ] No 404 errors
- [ ] No console errors
- [ ] Assets load correctly
- [ ] Responsive design works

### ✅ Visual Check

- [ ] Sidebar appears correctly
- [ ] Headers display properly
- [ ] Colors are correct (purple theme)
- [ ] Borders are thin (1px)
- [ ] Hover effects work
- [ ] Points badge shows
- [ ] Avatar displays

### ✅ Performance Check

- [ ] Pages load quickly (< 2 seconds)
- [ ] No excessive file sizes
- [ ] No render-blocking resources
- [ ] Smooth interactions

---

## Rollback Plan

If issues are found after deployment:

### Quick Rollback

```bash
# Revert to previous commit
git revert HEAD

# Push revert
git push origin main
```

### Identify Issue

1. Check browser console for errors
2. Review git diff to see what changed
3. Test locally before re-deploying

### Fix and Re-deploy

1. Make necessary fixes
2. Test thoroughly locally
3. Commit with detailed message
4. Push and verify

---

## Stakeholder Communication

### Before Deployment

**Email template:**

```
Subject: Curator App Mockups - Design Update Ready

Hi [Stakeholder],

The curator app mockups have been updated to the new design style. 

Key changes:
- New sidebar navigation
- Purple color scheme (#7c3aed)
- Updated header with points badge
- Refined spacing and borders
- Enhanced hover effects

Files updated: 8 HTML mockups
Documentation: 4 comprehensive guides
Testing: Complete across browsers

Ready to deploy to GitHub Pages for review.

[Your name]
```

### After Deployment

**Email template:**

```
Subject: Curator App Mockups - Now Live

Hi [Stakeholder],

The updated curator app mockups are now live:
https://factory-labs.github.io/curator-app/

Updates include:
✅ Modern purple color scheme
✅ Fixed sidebar navigation
✅ Enhanced header components
✅ Consistent styling across all pages
✅ Comprehensive documentation

Please review and provide feedback.

Documentation available:
- README.md - Overview
- QUICK-REFERENCE.md - For developers
- VISUAL-CHANGES-GUIDE.md - Design details
- STYLING-UPDATE-REPORT.md - Complete report

[Your name]
```

---

## Troubleshooting

### Sidebar Not Showing

**Check:**
1. Is sidebar CSS included?
2. Is `<div class="sidebar">` present?
3. Is z-index correct? (should be 100)
4. Browser dev tools → Elements → Check for sidebar

**Fix:**
- Verify sidebar HTML was added
- Check CSS for `.sidebar` class
- Ensure no conflicting styles

### Purple Colors Not Applied

**Check:**
1. Search for old green colors (#10b981)
2. Check button classes (.btn-primary)
3. Verify focus states

**Fix:**
- Run find/replace again: #10b981 → #7c3aed
- Clear browser cache
- Check CSS specificity

### Content Off-Screen

**Check:**
1. Is main-wrapper present?
2. Is margin-left: 72px applied?
3. Check for absolute positioning issues

**Fix:**
- Verify `<div class="main-wrapper">` wraps content
- Check CSS for .main-wrapper class
- Remove conflicting margins

### Hover Effects Not Working

**Check:**
1. Border color changes on hover?
2. Shadow appears on hover?
3. Transition CSS present?

**Fix:**
- Verify hover CSS for cards
- Check transition: all 0.2s
- Ensure no !important conflicts

---

## Success Metrics

After deployment, verify:

- [ ] No 404 errors in Google Analytics
- [ ] Page load time < 2 seconds
- [ ] No JavaScript errors in console
- [ ] Mobile traffic works properly
- [ ] All stakeholders can access
- [ ] Positive feedback received

---

## Final Checklist

Before marking as complete:

- [ ] All HTML files deployed
- [ ] All documentation deployed
- [ ] Live site tested
- [ ] Stakeholders notified
- [ ] Feedback mechanism in place
- [ ] Next steps documented

---

## Contact Information

**Project**: Curator App / Bounty Mechanism  
**Organization**: Factory Labs Limited  
**Repository**: factory-labs/curator-app  
**Live URL**: https://factory-labs.github.io/curator-app/

---

**Deployment Date**: _______________  
**Deployed By**: _______________  
**Verified By**: _______________

---

✅ **Checklist Complete - Ready for Deployment**
