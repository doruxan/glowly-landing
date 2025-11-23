# 🚀 Deployment Checklist - Glowly Landing Page

## Pre-Deployment

### Files to Upload
- [x] `index.html` (updated with all SEO fixes)
- [x] `sitemap.xml` (NEW - must be in root directory)
- [x] `robots.txt` (NEW - must be in root directory)
- [ ] `og-image.png` (1200x630px - CREATE THIS!)
- [x] `icon.png` (existing, confirmed used)

### Image Requirements

#### og-image.png (Required for Social Sharing)
**Dimensions**: 1200 x 630 pixels  
**Format**: PNG or JPG  
**Max Size**: < 5MB  
**Content**: 
- Glowly branding/logo
- Tagline: "AI-Powered Skin Care App"
- Visually appealing gradient background
- No important content in outer 10% (may be cropped)

**Tools to Create**:
- Canva (https://canva.com) - Use "Facebook Post" template
- Figma - Use 1200x630 frame
- Photoshop/GIMP

---

## Post-Deployment Actions

### 1. Google Search Console (Priority: HIGH)
- [ ] Verify site ownership: https://search.google.com/search-console
- [ ] Submit sitemap: https://glowlyme.com/sitemap.xml
- [ ] Request indexing for homepage
- [ ] Check for mobile usability issues

### 2. Validation Tests (Priority: HIGH)
Run these immediately after deployment:

#### Structured Data
- [ ] https://search.google.com/test/rich-results
  - Enter: https://glowlyme.com/
  - Expected: ✅ SoftwareApplication, Organization, BreadcrumbList valid
  
- [ ] https://validator.schema.org/
  - Paste your HTML
  - Expected: ✅ No errors

#### Performance
- [ ] https://pagespeed.web.dev/
  - Test: https://glowlyme.com/
  - Target: 90+ mobile, 95+ desktop
  
- [ ] https://web.dev/measure/
  - Check Core Web Vitals
  - CLS should be < 0.1 (Good)

#### Social Sharing
- [ ] Facebook Debugger: https://developers.facebook.com/tools/debug/
  - Scrape URL to see preview
  - Image should show correctly
  
- [ ] Twitter Card Validator: https://cards-dev.twitter.com/validator
  - Preview should show og-image
  - @GlowlyApp should be mentioned
  
- [ ] LinkedIn Post Inspector: https://www.linkedin.com/post-inspector/
  - Verify preview looks correct

### 3. Manual Checks (Priority: MEDIUM)
- [ ] Test email signup form
- [ ] Verify phone mockup interactive demo works
- [ ] Check all anchor links (#home, #learn, #love, #join)
- [ ] Test on mobile devices (iOS Safari, Android Chrome)
- [ ] Verify dark mode toggle works
- [ ] Check loading speed on 3G connection

### 4. Social Media Setup (Priority: MEDIUM)
If accounts don't exist yet, create:
- [ ] Twitter: @GlowlyApp (update schema when created)
- [ ] Instagram: @glowlyapp (update schema when created)
- [ ] Post announcement about landing page
- [ ] Update schema URLs when real accounts exist

### 5. Analytics Setup (Priority: MEDIUM)
- [ ] Add Google Analytics 4 (if not already added)
- [ ] Add Facebook Pixel (for ad campaigns)
- [ ] Set up conversion tracking for email signups
- [ ] Create UTM parameters for social posts

---

## Week 1 Post-Launch

### Monitor These Daily
- [ ] Google Search Console - Any errors?
- [ ] PageSpeed Insights - Still 90+?
- [ ] Email signup rate - Track conversions
- [ ] Console errors in browser DevTools

### Expected Behavior
✅ **Google Search Console**: 
- Sitemap submitted and processed
- 3-4 pages indexed (home, #learn, #love)
- No mobile usability issues

✅ **PageSpeed Insights**:
- Mobile: 85-95 (depends on server)
- Desktop: 95-100
- Green scores on all Core Web Vitals

✅ **Rich Results**:
- SoftwareApplication snippet may appear
- BreadcrumbList may appear in search results
- Takes 1-7 days to show in actual search

---

## Common Issues & Fixes

### Issue: og-image not showing in social previews
**Fix**: 
1. Image must be publicly accessible
2. Use absolute URL: https://glowlyme.com/og-image.png
3. Clear cache in Facebook Debugger
4. Wait 24 hours for cache to expire

### Issue: Sitemap not found (404 error)
**Fix**:
1. Ensure sitemap.xml is in root directory (not /glowly-landing/)
2. Check file permissions (readable by web server)
3. Test direct URL: https://glowlyme.com/sitemap.xml

### Issue: robots.txt blocking crawlers
**Fix**:
1. Verify robots.txt allows all: `Allow: /`
2. Test with: https://support.google.com/webmasters/answer/6062598
3. No Disallow rules for homepage

### Issue: CLS (Layout Shift) still high
**Fix**:
1. Verify all images have width/height attributes
2. Check font loading (should have display=swap)
3. Add explicit height to hero section
4. Test on mobile with network throttling

### Issue: Structured data errors
**Fix**:
1. Use Rich Results Test to see specific error
2. Common: Missing required field
3. Verify JSON-LD is valid JSON (no trailing commas)
4. Check all URLs are absolute (https://...)

---

## When App Launches

### Update These in index.html

#### Add Download Links
```json
// In SoftwareApplication schema
"downloadUrl": "https://apps.apple.com/app/glowly/idXXXXXXXXX",
"installUrl": "https://play.google.com/store/apps/details?id=com.glowly.app"
```

#### Add Real Ratings (from stores)
```json
"aggregateRating": {
  "@type": "AggregateRating",
  "ratingValue": "4.7",
  "ratingCount": "823",
  "bestRating": "5",
  "worstRating": "1"
}
```

#### Update Availability
```json
// Change from PreOrder to:
"availability": "https://schema.org/InStock"
```

#### Add App Meta Tags
```html
<meta name="apple-itunes-app" content="app-id=XXXXXXXXXX">
<meta name="google-play-app" content="app-id=com.glowly.app">
```

---

## Success Metrics

### Week 1 Goals
- [ ] Indexed by Google (Search Console)
- [ ] PageSpeed: 90+ mobile
- [ ] No structured data errors
- [ ] 10+ email signups

### Month 1 Goals
- [ ] Ranking for "Glowly" (branded)
- [ ] 100+ email signups
- [ ] Social shares: 50+
- [ ] Backlinks: 5+

---

## Emergency Contacts

If something goes wrong:
1. Check Google Search Console first
2. Use PageSpeed Insights for performance issues
3. Validate structured data at schema.org
4. Test social previews in respective debuggers

---

## Files Changed in This Optimization

| File | Status | Location |
|------|--------|----------|
| index.html | ✅ Updated | /glowly-landing/ |
| sitemap.xml | ✅ Created | /glowly-landing/ |
| robots.txt | ✅ Created | /glowly-landing/ |
| og-image.png | ⚠️ Missing | /glowly-landing/ |

---

**Ready to Deploy**: Almost! Create og-image.png first.  
**Estimated Setup Time**: 30 minutes  
**SEO Impact Timeline**: 1-7 days for indexing, 2-4 weeks for ranking

Good luck! 🚀

