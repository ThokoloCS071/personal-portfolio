# personal-portfolio
**Modern Personal Portfolio** 🚀
                                          ** Portfolio Architecture**
This project is a static web application built using a clean separation of concerns: HTML5 for structure, CSS3 for styling and animations, and JavaScript (ES6) for DOM manipulation and interactivity.

🏗️ **1. Architecture Overview**

**HTML** 

The portfolio.html file uses semantic HTML5 tags to define the document structure:
Navigation: Uses a <nav> bar with a fixed position.
Sectioning: The page is divided into section blocks (#home, #about, #projects, #contact), each identified by an ID to enable Smooth Scroll navigation.
Data Display: Uses unordered lists (<ul>) within the "About" section to categorize skills and education.

**CSS **

The portfolio.css file handles the visual logic:
Layout: Utilizes CSS Flexbox for the header and contact sections, and CSS Grid for the Projects section to ensure a responsive, card-based layout.
Animations:The @keyframes morph animation creates a fluid, organic shape for the profile image by constantly shifting the border-radius.
Hover Effects: Card transitions use transform: translateY(-10px) and color shifts to provide immediate visual feedback.
Glassmorphism: The navigation bar uses backdrop-filter: blur(10px) and semi-transparent RGBA backgrounds to create a modern frosted-glass effect.
Responsiveness: Media queries trigger at 768px to stack horizontal columns vertically for mobile users.

**JavaScript**

The portfolio.js file manages the state of the UI without requiring page reloads.
Tab Switching Logic: The **opentab(tabname)** function handles the "Skills", "Experience", and "Education" sections.
It uses **document.getElementsByClassName** to loop through all tab links and content blocks, removing the .active-link and .active-tab classes from everything.
It then uses **event.currentTarget** and **document.getElementById(tabname)** to apply the active classes only to the selected element.
Event Handling: The **showMessage()** function prevents default link behavior and provides a JavaScript alert as a fallback for project links that aren't yet hosted.

⚙️ **2. Detailed Component Logic**

Navigation System
The navbar stays at the top of the viewport using position: fixed. 
The CSS property scroll-behavior: smooth in the * selector ensures that when a user clicks a nav link, the browser slides gracefully to the corresponding section ID instead of jumping.

**The "About" Tabs code**
**JavaScript**

// How the tab switching works:
function opentab(tabname){
    // 1. Hide all tab content and remove underline from links
    for (let tablink of tablinks){ tablink.classList.remove("active-link"); }
    for (let tabcontent of tabcontents){ tabcontent.classList.remove("active-tab"); }
}

**Responsive Grid**

The Project section uses an "auto-fit" approach:
code
CSS
grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
This logic tells the browser: "Create as many columns as possible that are at least 300px wide. If there isn't enough room, wrap them to the next line." This makes the site mobile-responsive without requiring dozens of media queries.

🚀 3. **Integration & Setup**
To modify or extend this code:
Adding a Skill: Simply add a new <li> inside the #skills div in the HTML.
Changing Theme Colors: Replace the hex codes in the CSS file.
Updating Projects: Copy/Paste a .project-card div; the CSS Grid will automatically position it correctly.


🛠️ **Dependencies**
FontAwesome: Loaded via a <script> tag to render the social and technical icons.
Google Fonts: Imported via <link> to load 'Inter' and 'Poppins'.
