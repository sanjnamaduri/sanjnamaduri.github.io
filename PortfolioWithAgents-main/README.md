# Modern Computer Science / Software Engineer Portfolio

A premium, glassmorphism-inspired personal portfolio website built specifically for high school and college students looking to present their software engineering, game dev, mobile app, and cybersecurity projects. 

Everything is fully self-contained in a single, lightweight, highly optimized file: `index.html`. It requires no installation, no build steps, and works instantly in any web browser.

---

## Table of Contents
1. [How to Open index.html](#1-how-to-open-indexhtml)
2. [How to Edit Text Content](#2-how-to-edit-text-content)
3. [How to Edit Accent Colors](#3-how-to-edit-accent-colors)
4. [How to Update Social Links](#4-how-to-update-social-links)
5. [How to Replace the Blob Placeholder with Your Photo](#5-how-to-replace-the-blob-placeholder-with-your-photo)
6. [How the Canvas Particle Animation Works](#6-how-the-canvas-particle-animation-works)
7. [Publishing Online via GitHub Pages (Free)](#7-publishing-online-via-github-pages-free)
8. [Publishing Online via Netlify Drag-and-Drop (Free)](#8-publishing-online-via-netlify-drag-and-drop-free)
9. [Future-Proof Folder Structure for Splitting Files](#9-future-proof-folder-structure-for-splitting-files)
10. [How to Add More Project Cards](#10-how-to-add-more-project-cards)

---

### 1. How to Open index.html

#### To View the Website:
- Simply **double-click the `index.html` file** in your local directory. It will instantly open in your default browser (Chrome, Safari, Firefox, Edge).
- As you make changes to the source code, save the file and click **Refresh** (`F5` or `Cmd + R`) in the browser tab to see updates.

#### To Edit the Website:
- Open `index.html` using any plain-text editor.
- **Recommended**: Download and use [Visual Studio Code (VS Code)](https://code.visualstudio.com/) which is free and has built-in code highlighting. Alternatively, you can use Sublime Text, Notepad (Windows), or TextEdit (Mac).

---

### 2. How to Edit Text Content

To make customization easy, the code is annotated with comments:
`<!-- [EDIT] -->`

1. Open `index.html` in your text editor.
2. Search for the word `[EDIT]` (press `Ctrl + F` on Windows or `Cmd + F` on Mac).
3. Change the text directly below or surrounding the comment (e.g., your name, location, graduation class, GPA, SAT, and biography details).
4. Save the file and refresh your browser.

---

### 3. How to Edit Accent Colors

The page comes with 5 active color picker swatches in the top-right corner of the navigation bar. The selected accent color is automatically remembered by the browser using `localStorage`.

If you want to edit the colors of these default swatches:
1. Open `index.html` and look for the swatch button definitions inside the `<div class="accent-picker">` block:
   ```html
   <button class="swatch orange active" data-color="#ff6b00" data-color-rgb="255, 107, 0" style="background-color: #ff6b00;" ...></button>
   ```
2. Replace the color values (both HEX codes like `#ff6b00` and comma-separated RGB values like `255, 107, 0`) with your preferred color codes. 
   - *Example*: To make the first swatch a custom gold color, use `data-color="#ffd700"`, `data-color-rgb="255, 215, 0"`, and `style="background-color: #ffd700;"`.

---

### 4. How to Update Social Links

Scroll to the bottom of `index.html` or search for the `social-grid` container class:
1. Locate the anchor tags representing your contact buttons:
   ```html
   <a href="mailto:madurisanjna@gmail.com" class="social-btn" ...>Email</a>
   <a href="https://github.com/sanjnamaduri" class="social-btn" ...>GitHub</a>
   ```
2. Replace the `href="..."` URL with your own credentials:
   - For email, keep the `mailto:` prefix (e.g., `mailto:your.email@gmail.com`).
   - For social profiles, paste your full profile link (e.g., `https://linkedin.com/in/username`).
   - For your resume, place your PDF file (e.g. `resume.pdf`) in the same folder as `index.html`, and set the link to `href="resume.pdf"`.

---

### 5. How to Replace the Blob Placeholder with Your Photo

By default, the about section features a beautiful constantly-morphing gradient blob labeled "Photo Placeholder". When you are ready to replace it with a real photo:

1. Save your photo (e.g., a square headshot named `headshot.jpg`) into the **same directory** as `index.html`.
2. Open `index.html` and search for the comment `REPLACE THE BLOB PLACEHOLDER WITH YOUR PHOTO`.
3. Locate this code block:
   ```html
   <div class="blob-placeholder" id="blob-placeholder">
     ...
   </div>
   ```
4. Comment out or delete that entire `<div>` block.
5. Uncomment the image element below it:
   ```html
   <!-- Before -->
   <!-- <img class="about-photo" src="headshot.jpg" alt="Sanjna Maduri"> -->

   <!-- After (Uncommented) -->
   <img class="about-photo" src="headshot.jpg" alt="Sanjna Maduri">
   ```
6. Ensure that the `src` attribute matches your photo's exact filename (filenames are case-sensitive: `headshot.jpg` vs `headshot.JPG`). The CSS will automatically apply the morphing shape, borders, and glowing accents to your image!

---

### 6. How the Canvas Particle Animation Works

The backdrop of the hero section is driven by a high-performance, interactive particle network system built using the HTML5 `<canvas>` API and vanilla JavaScript.

- **Initialization**: When the page loads, the script checks your browser screen size. To optimize mobile performance, it dynamically scales down the node count (e.g., 40 nodes on mobile screens vs. 100 on desktop screens).
- **Animation Loop**: A loop runs at a smooth 60 FPS using `requestAnimationFrame`, continuously updating particle coordinates and rendering circles onto the canvas.
- **Connected Networks**: A nested loop calculates the distance between every pair of particles. If two particles get close enough, it draws a line connecting them. The line's opacity is proportional to how close they are, giving it a fading, organic web feel.
- **Mouse Repulsion**: The script tracks mouse movements globally. If a particle enters a radius of 130px around your mouse cursor, a repulsion force vector is calculated, gently pushing the particle away.
- **Theme/Accent Response**: The drawing loop dynamically retrieves the active accent color (`--accent-rgb`) from CSS variables on every redraw. This allows the particles to recolor instantly whenever you select a new swatch.

---

### 7. Publishing Online via GitHub Pages (Free)

Using GitHub Pages is highly recommended because it shows college admissions officers and recruiters that you understand standard developer Git workflows.

1. Sign up for a free account at [GitHub](https://github.com).
2. Create a new repository named exactly: `yourusername.github.io` (replace `yourusername` with your actual GitHub username in lowercase).
3. Select **Public** as the repository visibility.
4. Click **Upload an existing file** and drag in your `index.html` (and your headshot and resume PDF, if you added them).
5. Click **Commit changes** to save them to the repository.
6. Go to the repository **Settings** $\rightarrow$ **Pages** (in the left sidebar menu).
7. Under "Build and deployment", select **Deploy from a branch**. Under "Branch", set it from *None* to **main** (or `/root`) and click **Save**.
8. Wait 1-2 minutes. Your website will be live at: `https://yourusername.github.io`

---

### 8. Publishing Online via Netlify Drag-and-Drop (Free)

Netlify is the fastest way to host your site without touching command line tools.

1. Go to [Netlify Drop](https://app.netlify.com/drop).
2. Drag and drop the **entire folder** containing your `index.html` (along with your headshot and resume PDF) onto the page.
3. Netlify will instantly upload your files and generate a live link (e.g., `https://random-name.netlify.app`).
4. To customize the name of your link (e.g., `https://sanjnamaduri.netlify.app`), create a free Netlify account, navigate to **Site Settings** $\rightarrow$ **Domain Management** $\rightarrow$ **Custom Domains**, and edit the site name.

---

### 9. Future-Proof Folder Structure for Splitting Files

If your project grows and you want to organize it, you can split the single file into a structured multi-file setup:

```text
my-portfolio/
│
├── index.html            # Main markup (referencing external styles and scripts)
├── README.md             # Documentation
│
├── css/
│   └── styles.css        # Clean CSS styles (moved from <style>)
│
├── js/
│   └── script.js         # JavaScript logic & Canvas physics (moved from <script>)
│
└── assets/
    ├── images/
    │   └── headshot.jpg  # Profile picture
    └── documents/
        └── resume.pdf    # Downloadable resume
```

#### How to link them in `index.html`:
- To link your CSS, add this inside the `<head>` block:
  ```html
  <link rel="stylesheet" href="css/styles.css">
  ```
- To link your JS, add this before the closing `</body>` tag:
  ```html
  <script src="js/script.js"></script>
  ```

---

### 10. How to Add More Project Cards

If you build more projects in the future, you can add them to your showcase grid:

1. Open `index.html` and find the `<div class="projects-grid">` element.
2. Copy one of the project card divs:
   ```html
   <div class="project-card">
     ...
   </div>
   ```
3. Paste the copied code directly above or below another card inside the grid.
4. Customize the project card contents:
   - **Background Gradients**: Change the thumbnail gradient class on the thumbnail div (choose from `gradient-blue-purple`, `gradient-orange-red`, `gradient-pink-purple`, or `gradient-green-teal`).
   - **Icons**: Replace the SVG path inside the thumbnail with any SVG icon matching your project topic (you can copy inline SVGs from websites like [Heroicons](https://heroicons.com/)).
   - **Text**: Update the project title, description, and technology tags.
   - **Links**: Update the GitHub and Demo URL attributes (`href`).
