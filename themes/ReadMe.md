# Theming Support for Bookerei

> **Good news!** Custom theming is now available in app version **v1.9**!

You can customize your theme in the app settings. Follow this guide to create and apply your own themes.

## Table of Contents

- [Theming Support for Bookerei](#theming-support-for-bookerei)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Getting Started](#getting-started)
  - [Theme Structure](#theme-structure)
  - [Color Variables](#color-variables)
    - [General](#general)
    - [Buttons](#buttons)
    - [Sidebar](#sidebar)
    - [Top Bar](#top-bar)
    - [Search Box](#search-box)
    - [Front Card](#front-card)
    - [Tabs and Toolbar](#tabs-and-toolbar)
    - [Book Search Results](#book-search-results)
    - [Book Details](#book-details)
  - [Creating Your Own Theme](#creating-your-own-theme)
  - [Testing Your Theme](#testing-your-theme)
  - [Submitting Your Theme](#submitting-your-theme)
  - [Theme Example](#theme-example)

## Introduction

Theming in Bookerei allows you to customize the appearance of the application. Themes are defined using CSS variables that control colors, backgrounds, shadows, and other visual elements of the application.

## Getting Started

To create a theme for Bookerei, you'll need:

1. Basic knowledge of CSS
2. A text editor
3. Understanding of CSS variables (custom properties)

## Theme Structure

Each theme is defined in a separate CSS file. The file should:

- Be named after your theme (e.g., `mytheme.css`)
- Contain CSS variables inside a selector based on your theme name
- Include all required variables for proper application styling

## Color Variables

Your theme must define the following groups of variables:

### General

```css
--app-bg-primary: /* Main application background */
--app-bg-secondary: /* Dialog and offcanvas background */
--app-bg-tertiary: /* Hover background, text group icon background */

--app-text-color-primary: /* Text color readable on bg-primary */
--app-text-color-primary-muted: /* Muted text readable on bg-primary */
--app-text-color-secondary: /* Text color readable on bg-secondary */
--app-text-color-tertiary: /* Text color readable on bg-tertiary */

--app-highlight-color: /* Main highlight color */
--app-highlight-color-secondary: /* Secondary highlight color */

--app-link-color: /* Link color */
--app-link-hover-color: /* Link hover color */
```

### Buttons

```css
--app-button-primary-background: /* Background for primary buttons */
--app-button-primary-background-hover: /* Hover background for primary buttons */
--app-button-primary-text-color: /* Text color for primary buttons */
--app-button-primary-text-hover: /* Hover text color for primary buttons */

--app-button-secondary-background: /* Background for secondary buttons */
--app-button-secondary-background-hover: /* Hover background for secondary buttons */
--app-button-secondary-text-color: /* Text color for secondary buttons */
--app-button-secondary-text-hover: /* Hover text color for secondary buttons */
```

### Sidebar

```css
--app-sidebar-background: /* Sidebar background */
--app-sidebar-width: /* Sidebar width */
--app-sidebar-border: /* Sidebar border */
--app-sidebar-shadow: /* Sidebar shadow */
--app-sidebar-menu-item-color: /* Menu item color */
--app-sidebar-menu-item-hover-background: /* Menu item hover background */
--app-sidebar-menu-item-hover-color: /* Menu item hover color */
--app-sidebar-menu-item-active-color: /* Active menu item color */
--app-sidebar-menu-item-active-border-color: /* Active menu item border color */
--app-sidebar-menu-item-active-background: /* Active menu item background */
```

### Top Bar

```css
--app-topbar-background: /* Top bar background */
--app-topbar-shadow: /* Top bar shadow */
--app-topbar-border: /* Top bar border */
--app-topbar-margin-start: /* Top bar start margin */
```

### Search Box

```css
--app-search-input-background-color: /* Search input background */
--app-search-input-text-color: /* Search input text color */
--app-search-input-placeholder-color: /* Search input placeholder color */
--app-search-input-border: /* Search input border */
--app-search-input-focus-border: /* Search input focus border */
--app-search-input-focus-boxshadow: /* Search input focus box shadow */
--app-search-results-border-bottom: /* Search results border bottom */
--app-search-results-item-background-color: /* Search results item background */
--app-search-results-item-text-color: /* Search results item text color */
--app-search-results-item-hover-text-color: /* Search results item hover text color */
--app-search-results-item-active-text-color: /* Search results item active text color */
--app-search-results-item-hover-background-color: /* Search results item hover background */
```

### Front Card

```css
--app-frontcard-title-background: /* Front card title background */
--app-frontcard-title-text-color: /* Front card title text color */
--app-frontcard-text-color: /* Front card text color */
--app-carousel-next-image: /* Carousel next image */
--app-carousel-prev-image: /* Carousel previous image */
```

### Tabs and Toolbar

```css
--app-tab-text-color: /* Tab text color */
--app-tab-active-text-color: /* Active tab text color */

--app-toolbar-button-bg: /* Toolbar button background */
--app-toolbar-button-text-color: /* Toolbar button text color */
--app-toolbar-button-hover-bg: /* Toolbar button hover background */
--app-toolbar-button-disabled-text-color: /* Toolbar button disabled text color */
--app-toolbar-button-active-bg: /* Toolbar button active background */
--app-toolbar-button-active-text-color: /* Toolbar button active text color */
```

### Book Search Results

```css
--app-bookresult-list-odditem-background: /* Book result list odd item background */
--app-bookresult-list-odditem-hover-background: /* Book result list odd item hover background */
--app-bookresult-list-title-text-color: /* Book result list title text color */
--app-bookresult-list-author-text-color: /* Book result list author text color */
--app-bookresult-list-date-text-color: /* Book result list date text color */
```

### Book Details

```css
--app-bookdetails-background: /* Book details background */
--app-bookdetails-title-text-color: /* Book details title text color */
--app-bookdetails-shadow: /* Book details shadow */
--app-bookdetails-border-radius: /* Book details border radius */
--app-bookdetails-label-background-color: /* Book details label background color */
--app-bookdetails-label-text-color: /* Book details label text color */
```

## Creating Your Own Theme

Follow these steps to create your own theme:

1. **Start with a template:**
   Copy an existing theme file like `bookerei.css` and rename it to your theme name (e.g., `mytheme.css`).

2. **Update the selector:**
   Change the selector to match your theme name:

   ```css
   body[data-theme="MyTheme"] {
       /* your theme variables here */
   }
   ```

3. **Customize the variables:**
   Modify the CSS variables to create your unique look and feel.

4. **Add RTL (Right-to-Left) support if needed:**

   ```css
   html[dir="rtl"] body[data-theme="MyTheme"] {
       /* RTL-specific overrides */
   }
   ```

5. **Add metadata:**
   Include a comment at the top with your information:

   ```css
   /*
   Author: Your Name
   Url: https://your-website.com
   */
   ```

## Testing Your Theme

Once v1.9 is released:

1. Open Themes in Bookerei
2. Use the "Import Theme" option to import your CSS file
3. Select your theme from the available options
4. Test the application with your theme applied to ensure all elements are styled correctly

> **Note:** There's no need to place the file in the themes directory - the Bookerei app provides an option to import themes directly.

## Submitting Your Theme

To share your theme with the Bookerei community:

1. **Option 1: Create a Pull Request (Recommended)**
   - Fork the Bookerei repository on GitHub
   - Add your theme CSS file to the themes folder
   - Create a pull request with a description of your theme

2. **Option 2: Share Your Theme File**
   - Share your CSS file with other Bookerei users
   - They can use the "Import Theme" option in the app settings
   - Send your CSS file to the project maintainers for potential inclusion in future releases

## Theme Example

Here's a simplified version of the default Bookerei theme:

```css
/*
Author: Bookerei
Url: https://pickandroll.dev/bookerei
*/

body[data-theme="Bookerei"] {
    /* GENERAL */
    --app-bg-primary: #271d1a url(...) repeat fixed; /* App background */
    --app-bg-secondary: rgb(240, 236, 224, 0.9); /* Dialog, Offcanvas background */
    --app-bg-tertiary: #f1efe9; /* Hover background, text group icon background */

    --app-text-color-primary: #fdfcea; /* Readable on bg-primary */
    --app-text-color-primary-muted: rgb(255, 255, 255, 0.6); /* Readable on bg-primary, muted */
    --app-text-color-secondary: rgb(29, 29, 28); /* Readable on bg-secondary */
    --app-text-color-tertiary: rgb(82, 46, 16); /* Readable on bg-tertiary */

    --app-highlight-color: #d92310; /* Highlight color for buttons and links */
    --app-highlight-color-secondary: #d9241083; /* Secondary highlight color */

    --app-link-color: burlywood; /* Link color */
    --app-link-hover-color: var(--app-highlight-color); /* Link hover color */
    
    /* Additional CSS variables for other components... */
}

html[dir="rtl"] body[data-theme="Bookerei"] {
    --app-topbar-background: linear-gradient(to left, #271D1A 0%, #3F3F3F 80%, #9a8478 200%), 
        linear-gradient(to right, rgba(255,255,255,0.40) 0%, rgba(0,0,0,0.25) 200%);
}
```

For a complete example, refer to the `bookerei.css` file included in the themes directory.
