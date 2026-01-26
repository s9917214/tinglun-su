# GEMINI.md - Project Overview

This file provides a comprehensive overview of the academic portfolio website project for Ting-Lun Su.

## Project Overview

This is a static, single-page personal portfolio website designed to showcase the academic and professional achievements of Ting-Lun Su. The project is built using standard web technologies: HTML, CSS, and JavaScript. It is designed to be easily customizable and deployable on static hosting services like GitHub Pages.

### Key Features:

-   **Responsive Design:** The layout is fully responsive and adapts to various screen sizes, including desktops, tablets, and mobile devices.
-   **Dynamic Content:** The website includes several dynamic features powered by JavaScript, such as:
    -   Smooth scrolling for navigation links.
    -   Active section highlighting in the navigation bar based on scroll position.
    -   A mobile-friendly hamburger menu.
    -   Animated counters for statistics.
    -   Lazy loading for embedded videos.
    -   An intelligent photo gallery system that dynamically detects and displays award photos in different layouts (single, collage, grid, carousel) based on the number of images found in the corresponding directory.
-   **Bilingual Support:** The UI includes a language switcher, although the full translation logic is not yet implemented.
-   **Print-Friendly:** The stylesheet includes a print media query to ensure the portfolio can be easily printed.

## Running the Project

This is a static website with no build process. To run the project locally, simply open the `index.html` file in a web browser.

For development, it is recommended to use a local web server with live reload capabilities, such as the "Live Server" extension for Visual Studio Code.

## Project Structure

-   `index.html`: The main HTML file containing the structure and content of the website.
-   `style.css`: The stylesheet that defines the visual presentation, including layout, colors, and typography.
-   `script.js`: The JavaScript file that provides interactivity and dynamic features.
-   `images/`: A directory containing all the images used in the project, such as the profile picture, award photos, and patent illustrations.
-   `README.md`: A detailed guide on how to use and customize the website template (in Traditional Chinese).
-   Other `.md` files (`VIDEO_GUIDE.md`, etc.): Supplementary documentation explaining specific features.

## Development Conventions

-   **CSS:** The project uses a BEM-like naming convention for CSS classes (e.g., `project-card`, `project-header`). It uses CSS variables (`:root`) for theming and maintaining a consistent color palette.
-   **JavaScript:** The code is written in modern vanilla JavaScript (ES6+). It is well-commented and organized into logical sections for different features. It includes performance optimizations like debouncing for scroll and resize events.
-   **HTML:** The HTML is semantic and well-structured.
-   **Image Management:** Award photos are organized into subdirectories by year within `images/awards/`. The `script.js` file contains logic to automatically detect these images and generate appropriate gallery layouts. To add photos for a specific award year, place them in the corresponding folder (e.g., `images/awards/2025/`). The script will look for files named `award1.jpg`, `award2.jpg`, etc.
