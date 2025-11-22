# K-Nails Website 💅

A professional, interactive static website for Keren's nail business (knails.co.il).

## Features

✨ **Modern & Responsive Design**
- Fully responsive layout that works on all devices
- Beautiful gradient hero section
- Smooth animations and transitions
- Mobile-friendly navigation with hamburger menu

💅 **Services Showcase**
- Gel nails technique
- Professional manicure services
- Custom press-on nails on order

📚 **Educational Content**
- Comprehensive FAQ section covering:
  - Gel vs. Acrylic nails
  - Nail care tips
  - Service explanations
  - Maintenance guidelines

🔗 **Social Media Integration**
- Instagram link (placeholder - update when ready)
- Facebook link (placeholder - update when ready)
- WhatsApp integration for quick contact

⚡ **Interactive Features**
- Smooth scrolling navigation
- FAQ accordion (click to expand/collapse)
- Active navigation highlighting
- Mobile menu toggle
- Fade-in animations on scroll

## Files Structure

```
knails/
├── assets/
│   ├── css/
│   │   └── style.css       # All styling (responsive, modern design)
│   ├── js/
│   │   └── script.js       # Interactive features
│   └── images/             # Folder for images (photos, gallery, etc.)
├── index.html              # Main homepage
├── 404.html                # Custom 404 error page (nail-themed)
├── error.html              # Generic error page (500, 503, etc.)
└── README.md               # This file
```

## How to Use

### 1. Local Testing

Simply open `index.html` in your web browser. No server required!

```bash
# Open with default browser
open index.html       # macOS
xdg-open index.html   # Linux
start index.html      # Windows
```

### 2. Deploying to knails.co.il

You can deploy this website using various methods:

#### Option A: Traditional Web Hosting
1. Upload all files and folders to your web hosting via FTP
2. Make sure files are in the public_html or www directory
3. Configure error pages in your hosting control panel (see Error Pages Setup below)
4. Visit knails.co.il

#### Option B: GitHub Pages (Free)
1. Create a GitHub repository
2. Push all files to the repository
3. Enable GitHub Pages in repository settings
4. Configure custom domain (knails.co.il) in settings

#### Option C: Netlify (Free, Easy)
1. Create account at netlify.com
2. Drag and drop the entire folder
3. Configure custom domain (knails.co.il)

#### Option D: Vercel (Free)
1. Create account at vercel.com
2. Import your project
3. Configure custom domain (knails.co.il)

### 3. Error Pages Setup

The website includes custom, business-themed error pages:

**404.html** - For "Page Not Found" errors
- Friendly, on-brand message with nail theme
- Links back to homepage and services
- Floating nail decorations and animations

**error.html** - For server errors (500, 503, etc.)
- Generic error page for technical issues
- Auto-retry functionality
- Quick contact options

#### Setting up error pages:

**For Apache servers (.htaccess):**
Create a `.htaccess` file in your root directory:
```apache
ErrorDocument 404 /404.html
ErrorDocument 500 /error.html
ErrorDocument 503 /error.html
```

**For Nginx:**
Add to your nginx config:
```nginx
error_page 404 /404.html;
error_page 500 502 503 504 /error.html;
```

**For Netlify:**
Create a `netlify.toml` file:
```toml
[[redirects]]
  from = "/*"
  to = "/404.html"
  status = 404
```

**For Vercel:**
Create a `vercel.json` file:
```json
{
  "routes": [
    { "handle": "filesystem" },
    { "src": "/(.*)", "status": 404, "dest": "/404.html" }
  ]
}
```

## Customization Guide

### Update Social Media Links

In `index.html`, find these sections and update the `href` values:

```html
<!-- Instagram -->
<a href="#" class="social-link instagram" target="_blank">
<!-- Change to: -->
<a href="https://instagram.com/your_username" class="social-link instagram" target="_blank">

<!-- Facebook -->
<a href="#" class="social-link facebook" target="_blank">
<!-- Change to: -->
<a href="https://facebook.com/your_page" class="social-link facebook" target="_blank">

<!-- WhatsApp -->
<a href="https://wa.me/972" class="btn btn-whatsapp" target="_blank">
<!-- Change to: -->
<a href="https://wa.me/972XXXXXXXXX" class="btn btn-whatsapp" target="_blank">
<!-- Replace 972XXXXXXXXX with the full phone number including country code -->
```

### Update Phone Number

In `index.html`, find:

```html
<a href="tel:+972" class="btn btn-secondary">התקשרי עכשיו</a>
```

Change to:

```html
<a href="tel:+972XXXXXXXXX" class="btn btn-secondary">התקשרי עכשיו</a>
```

### Update Location

In `index.html`, find the location section and add the actual address:

```html
<div class="contact-card">
    <i class="fas fa-map-marker-alt"></i>
    <h3>מיקום</h3>
    <p>הסטודיו נמצא ב...</p>
    <p class="location-text">(הכתובת תעודכן בקרוב)</p>
</div>
```

### Add Keren's Photo

1. Add an image file (e.g., `keren.jpg`) to the `assets/images/` folder
2. In `index.html`, find the `.image-placeholder` div and replace with:

```html
<div class="about-image">
    <img src="assets/images/keren.jpg" alt="קרן - אמנית ציפורניים מקצועית" style="width: 100%; max-width: 400px; border-radius: 12px; box-shadow: 0 4px 8px rgba(0,0,0,0.15);">
</div>
```

### Add Gallery Section (Optional)

To add a photo gallery of nail work, add this section in `index.html` before the FAQ section:

```html
<section id="gallery" class="gallery">
    <div class="container">
        <h2 class="section-title">גלריית עבודות</h2>
        <p class="section-subtitle">דוגמאות מעבודות שבוצעו</p>
        <div class="gallery-grid">
            <img src="assets/images/work1.jpg" alt="עבודת ציפורניים 1">
            <img src="assets/images/work2.jpg" alt="עבודת ציפורניים 2">
            <img src="assets/images/work3.jpg" alt="עבודת ציפורניים 3">
            <!-- Add more images to assets/images/ folder -->
        </div>
    </div>
</section>
```

And add this CSS to `assets/css/style.css`:

```css
.gallery {
    background-color: var(--white);
}

.gallery-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: var(--spacing-sm);
}

.gallery-grid img {
    width: 100%;
    height: 250px;
    object-fit: cover;
    border-radius: 8px;
    box-shadow: var(--shadow-sm);
    transition: var(--transition);
    cursor: pointer;
}

.gallery-grid img:hover {
    transform: scale(1.05);
    box-shadow: var(--shadow-md);
}
```

### Change Colors

In `assets/css/style.css`, modify the color variables at the top:

```css
:root {
    --primary-color: #d4417c;      /* Main pink color */
    --primary-dark: #b8325f;       /* Darker pink */
    --secondary-color: #f8b5d3;    /* Light pink */
    --accent-color: #ffd4e5;       /* Very light pink */
}
```

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Technologies Used

- HTML5
- CSS3 (Grid, Flexbox, Custom Properties)
- Vanilla JavaScript (ES6+)
- Font Awesome Icons
- Google Fonts (Heebo, Assistant)

## SEO Optimization

The website includes:
- Semantic HTML5 markup
- Meta descriptions and keywords
- Proper heading hierarchy
- RTL (Right-to-Left) support for Hebrew
- Mobile-responsive design
- Fast loading times

## Tips for Best Results

1. **Add high-quality images** of Keren's work to showcase skills
2. **Update contact information** as soon as social media pages are created
3. **Consider adding testimonials** from satisfied customers
4. **Add a booking system** if needed (can integrate Calendly or similar)
5. **Set up Google Analytics** to track visitors
6. **Create a blog section** for nail care tips (optional)

## Support

For questions or issues with the website, you can:
- Check the code comments in each file
- Modify the FAQ section to add more questions
- Adjust styling in `style.css` to match your preferences

---

**Built with ❤️ for K-Nails**

Good luck with Keren's nail business! 💅✨
