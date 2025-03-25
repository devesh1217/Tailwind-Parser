# Tailwind CSS Documentation

## Table of Contents
1. [Introduction](#introduction)
2. [Getting Started](#getting-started)
3. [Core Concepts](#core-concepts)
4. [Utility Classes](#utility-classes)
5. [Colors](#colors)
6. [Font Sizes](#font-sizes)
7. [Spacing](#spacing)
8. [Responsive Design](#responsive-design)
9. [Dark Mode](#dark-mode)
10. [Customization](#customization)
11. [Resources](#resources)

## Introduction

Tailwind CSS is a utility-first CSS framework that allows you to build modern websites without ever leaving your HTML. Unlike traditional frameworks like Bootstrap or Foundation, Tailwind doesn't provide pre-designed components. Instead, it gives you low-level utility classes that let you build completely custom designs.

### Key Benefits

- **Utility-First Approach**: Apply styles directly in your markup for faster development
- **Highly Customizable**: Tailor the framework to your design system
- **Responsive Design**: Built-in responsive modifiers for different screen sizes
- **Component-Friendly**: Extract reusable patterns with directives or component libraries
- **Modern Features**: Support for dark mode, animations, transitions, and more
- **Performance Focused**: Generates optimized CSS with PurgeCSS built-in

## Getting Started

### Installation

There are several ways to install Tailwind CSS:

**Option 1: Using npm**

```bash
npm install -D tailwindcss
npx tailwindcss init
```

**Option 2: Using CDN (not recommended for production)**

```html
<script src="https://cdn.tailwindcss.com"></script>
```

### Basic Configuration

Create a `tailwind.config.js` file:

```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./src/**/*.{html,js,jsx,ts,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

Create a CSS file that includes Tailwind's directives:

```css
/* src/input.css */
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Process your CSS with Tailwind CLI:

```bash
npx tailwindcss -i ./src/input.css -o ./dist/output.css --watch
```

Link the output CSS file in your HTML:

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="/dist/output.css" rel="stylesheet">
</head>
<body>
  <h1 class="text-3xl font-bold text-blue-500">
    Hello world!
  </h1>
</body>
</html>
```

## Core Concepts

### Utility-First Philosophy

Tailwind's approach involves using small, single-purpose utility classes to build complex components:

```html
<!-- Traditional CSS approach -->
<div class="chat-notification">
  <div class="chat-notification-logo-wrapper">
    <img class="chat-notification-logo" src="/img/logo.svg" alt="ChitChat Logo">
  </div>
  <div class="chat-notification-content">
    <h4 class="chat-notification-title">ChitChat</h4>
    <p class="chat-notification-message">You have a new message!</p>
  </div>
</div>

<!-- Tailwind CSS approach -->
<div class="p-6 max-w-sm mx-auto bg-white rounded-xl shadow-md flex items-center space-x-4">
  <div class="shrink-0">
    <img class="h-12 w-12" src="/img/logo.svg" alt="ChitChat Logo">
  </div>
  <div>
    <div class="text-xl font-medium text-black">ChitChat</div>
    <p class="text-gray-500">You have a new message!</p>
  </div>
</div>
```

### Naming Convention

Tailwind uses a predictable naming pattern:
- `{property}-{value}` for most utilities
- `{property}-{modifier}-{value}` for variants
- `{breakpoint}:{property}-{value}` for responsive utilities

Examples:
- `text-center`: Centers text
- `bg-blue-500`: Sets background color to blue (500 intensity)
- `hover:underline`: Applies underline on hover
- `md:flex`: Applies flex display at medium screen size and above

## Utility Classes

### Typography

Control text appearance with utilities for font family, size, weight, color, and more:

```html
<p class="font-sans text-lg font-medium text-gray-800 leading-relaxed tracking-wide">
  Beautifully styled text with Tailwind CSS
</p>
```

Key typography classes:
- Font family: `font-sans`, `font-serif`, `font-mono`
- Font size: `text-xs`, `text-sm`, `text-base`, `text-lg`, `text-xl`, `text-2xl`...
- Font weight: `font-thin`, `font-light`, `font-normal`, `font-medium`, `font-bold`...
- Text color: `text-{color}-{shade}` (e.g., `text-blue-500`)
- Text alignment: `text-left`, `text-center`, `text-right`, `text-justify`
- Line height: `leading-none`, `leading-tight`, `leading-normal`, `leading-relaxed`...
- Letter spacing: `tracking-tighter`, `tracking-tight`, `tracking-normal`, `tracking-wide`...
- Text decoration: `underline`, `line-through`, `no-underline`
- Text transform: `uppercase`, `lowercase`, `capitalize`, `normal-case`

### Colors

Tailwind provides a comprehensive color palette. Below is a table showcasing the default colors with their shades and actual color display.

| Color Name | Shade | Example |
|------------|-------|---------|
| Gray       | 50    | <div style="background-color: #f9fafb; width: 50px; height: 20px; display: inline-block;"></div> `#f9fafb` |
| Gray       | 100   | <div style="background-color: #f3f4f6; width: 50px; height: 20px; display: inline-block;"></div> `#f3f4f6` |
| Gray       | 200   | <div style="background-color: #e5e7eb; width: 50px; height: 20px; display: inline-block;"></div> `#e5e7eb` |
| Blue       | 500   | <div style="background-color: #3b82f6; width: 50px; height: 20px; display: inline-block;"></div> `#3b82f6` |
| Red        | 500   | <div style="background-color: #ef4444; width: 50px; height: 20px; display: inline-block;"></div> `#ef4444` |
| Green      | 500   | <div style="background-color: #10b981; width: 50px; height: 20px; display: inline-block;"></div> `#10b981` |

For the full palette, refer to the [Tailwind CSS Color Documentation](https://tailwindcss.com/docs/customizing-colors).

---

## Font Sizes

Tailwind provides a range of font sizes. Below is a table with examples:

| Class       | Font Size | Example Text |
|-------------|-----------|--------------|
| `text-xs`   | 0.75rem   | <span style="font-size: 0.75rem;">Extra Small Text</span> |
| `text-sm`   | 0.875rem  | <span style="font-size: 0.875rem;">Small Text</span> |
| `text-base` | 1rem      | <span style="font-size: 1rem;">Base Text</span> |
| `text-lg`   | 1.125rem  | <span style="font-size: 1.125rem;">Large Text</span> |
| `text-xl`   | 1.25rem   | <span style="font-size: 1.25rem;">Extra Large Text</span> |
| `text-2xl`  | 1.5rem    | <span style="font-size: 1.5rem;">2XL Text</span> |
| `text-3xl`  | 1.875rem  | <span style="font-size: 1.875rem;">3XL Text</span> |

---

## Spacing

Tailwind's spacing utilities control padding, margin, and gap. Below is a table with examples:

| Class       | Value   | Example |
|-------------|---------|---------|
| `p-0`       | 0px     | Padding: 0px |
| `p-4`       | 1rem    | Padding: 1rem |
| `m-2`       | 0.5rem  | Margin: 0.5rem |
| `gap-6`     | 1.5rem  | Gap: 1.5rem |

---

## Responsive Design

Tailwind's responsive utilities allow you to apply styles at specific breakpoints. Below are examples:

| Breakpoint | Prefix | Min Width |
|------------|--------|-----------|
| `sm`       | `sm:`  | 640px     |
| `md`       | `md:`  | 768px     |
| `lg`       | `lg:`  | 1024px    |
| `xl`       | `xl:`  | 1280px    |

Example:
```html
<div class="text-base sm:text-lg md:text-xl lg:text-2xl xl:text-3xl">
  Responsive Text
</div>
```

---

## Dark Mode

Tailwind provides built-in support for dark mode:

```html
<div class="bg-white dark:bg-gray-800 text-gray-900 dark:text-white">
  This element changes colors in dark mode
</div>
```

### Configuration

Enable dark mode in your config:

```javascript
// tailwind.config.js
module.exports = {
  darkMode: 'media', // or 'class'
  // ...
}
```

Options:
- `'media'`: Uses the operating system preference via `@media (prefers-color-scheme: dark)`
- `'class'`: Manually toggle by adding the `dark` class to the `html` element

### Best Practices for Dark Mode

1. Use semantic color names in config (e.g., `primary`, `secondary`) rather than specific colors
2. Test both light and dark modes during development
3. Consider accessibility and contrast in both modes
4. Create reusable components that handle both modes consistently

## Customization

Tailwind is designed to be customized to match your design system.

### Configuration File

Modify the `tailwind.config.js` file to customize:

```javascript
module.exports = {
  content: [
    './src/**/*.{html,js,jsx,ts,tsx}',
  ],
  theme: {
    colors: {
      primary: '#FF6363',
      secondary: '#6B7280',
      // ...
    },
    extend: {
      spacing: {
        '128': '32rem',
        '144': '36rem',
      },
      borderRadius: {
        '4xl': '2rem',
      },
      fontFamily: {
        heading: ['Montserrat', 'sans-serif'],
        body: ['Open Sans', 'sans-serif'],
      },
    },
  },
  plugins: [
    require('@tailwindcss/forms'),
    require('@tailwindcss/typography'),
  ],
}
```

### Extending vs. Overriding

- Using `extend` adds to the default theme
- Setting properties directly (outside `extend`) replaces the defaults
- Consider extending first before completely replacing defaults

### Custom Utilities

Create custom utilities using the `@layer` directive:

```css
@layer utilities {
  .text-shadow {
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
  }
  .clip-path-triangle {
    clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
  }
}
```

### Custom Variants

Create custom variants with plugins:

```javascript
// tailwind.config.js
const plugin = require('tailwindcss/plugin')

module.exports = {
  // ...
  plugins: [
    plugin(function({ addVariant }) {
      addVariant('optional', '&:optional')
      addVariant('group-optional', ':merge(.group):optional &')
    })
  ],
}
```

### Recommended Plugins

- `@tailwindcss/forms`: Better form styles
- `@tailwindcss/typography`: Rich text formatting
- `@tailwindcss/aspect-ratio`: Aspect ratio utilities
- `@tailwindcss/line-clamp`: Text truncation utilities

## Components

While Tailwind is utility-first, there are several ways to create reusable components.

### Component Extraction

#### Using @apply

Extract repeated utility patterns with the `@apply` directive:

```css
@layer components {
  .btn-primary {
    @apply py-2 px-4 bg-blue-500 text-white font-semibold rounded-lg shadow-md hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-blue-400 focus:ring-opacity-75;
  }
}
```

#### Using JavaScript Components

For frameworks like React, Vue, or Angular, create component abstractions:

```jsx
// React component example
function Button({ type = 'primary', children }) {
  const styles = {
    primary: 'py-2 px-4 bg-blue-500 text-white font-semibold rounded-lg shadow-md hover:bg-blue-700',
    secondary: 'py-2 px-4 bg-gray-200 text-gray-800 font-semibold rounded-lg shadow-md hover:bg-gray-300',
  };

  return (
    <button className={styles[type]}>
      {children}
    </button>
  );
}
```

### Component Libraries

Consider using existing component libraries built with Tailwind:

- **Tailwind UI**: Official premium component library
- **DaisyUI**: Free component library with themes
- **Headless UI**: Unstyled, accessible components designed for Tailwind
- **Flowbite**: Open-source component library

## Layout Patterns

Common UI patterns implemented with Tailwind.

### Responsive Navigation

```html
<nav class="bg-gray-800 p-4">
  <div class="container mx-auto flex flex-wrap items-center justify-between">
    <!-- Logo -->
    <div class="flex items-center flex-shrink-0 text-white mr-6">
      <span class="font-semibold text-xl tracking-tight">Logo</span>
    </div>
    
    <!-- Mobile menu button -->
    <div class="block lg:hidden">
      <button id="nav-toggle" class="flex items-center px-3 py-2 border rounded text-gray-200 border-gray-400 hover:text-white hover:border-white">
        <svg class="fill-current h-3 w-3" viewBox="0 0 20 20"><path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z"/></svg>
      </button>
    </div>
    
    <!-- Desktop menu -->
    <div id="nav-content" class="w-full hidden flex-grow lg:flex lg:items-center lg:w-auto">
      <div class="text-sm lg:flex-grow">
        <a href="#" class="block mt-4 lg:inline-block lg:mt-0 text-gray-200 hover:text-white mr-4">
          Home
        </a>
        <a href="#" class="block mt-4 lg:inline-block lg:mt-0 text-gray-200 hover:text-white mr-4">
          Features
        </a>
        <a href="#" class="block mt-4 lg:inline-block lg:mt-0 text-gray-200 hover:text-white">
          About
        </a>
      </div>
      <div>
        <a href="#" class="inline-block text-sm px-4 py-2 leading-none border rounded text-white border-white hover:border-transparent hover:text-gray-800 hover:bg-white mt-4 lg:mt-0">Sign Up</a>
      </div>
    </div>
  </div>
</nav>
```

### Card Layout

```html
<div class="max-w-sm rounded overflow-hidden shadow-lg">
  <img class="w-full" src="/img/card-top.jpg" alt="Card image">
  <div class="px-6 py-4">
    <div class="font-bold text-xl mb-2">Card Title</div>
    <p class="text-gray-700 text-base">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam vitae justo in purus hendrerit fermentum.
    </p>
  </div>
  <div class="px-6 pt-4 pb-2">
    <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#tag1</span>
    <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#tag2</span>
  </div>
</div>
```

### Hero Section

```html
<div class="relative pt-16 pb-32 flex content-center items-center justify-center" style="min-height: 75vh;">
  <div class="absolute top-0 w-full h-full bg-center bg-cover" style="background-image: url('https://images.unsplash.com/photo-1557804506-669a67965ba0?ixlib=rb-1.2.1&auto=format&fit=crop&w=1267&q=80');">
    <span class="w-full h-full absolute opacity-75 bg-black"></span>
  </div>
  <div class="container relative mx-auto">
    <div class="items-center flex flex-wrap">
      <div class="w-full lg:w-6/12 px-4 ml-auto mr-auto text-center">
        <div class="pr-12">
          <h1 class="text-white font-semibold text-5xl">
            Your story starts with us.
          </h1>
          <p class="mt-4 text-lg text-gray-300">
            This is a simple hero unit, a simple jumbotron-style component for calling extra attention to featured content or information.
          </p>
          <a href="#" class="mt-8 inline-block px-6 py-3 bg-blue-600 text-white font-medium text-xs leading-tight uppercase rounded shadow-md hover:bg-blue-700 hover:shadow-lg">
            Get Started
          </a>
        </div>
      </div>
    </div>
  </div>
</div>
```

### Modal

```html
<div class="fixed inset-0 bg-gray-600 bg-opacity-50 overflow-y-auto h-full w-full" id="modal">
  <div class="relative top-20 mx-auto p-5 border w-96 shadow-lg rounded-md bg-white">
    <div class="mt-3 text-center">
      <div class="mx-auto flex items-center justify-center h-12 w-12 rounded-full bg-green-100">
        <svg class="h-6 w-6 text-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
        </svg>
      </div>
      <h3 class="text-lg leading-6 font-medium text-gray-900">Successful!</h3>
      <div class="mt-2 px-7 py-3">
        <p class="text-sm text-gray-500">
          Your account has been successfully created!
        </p>
      </div>
      <div class="items-center px-4 py-3">
        <button id="close-modal" class="px-4 py-2 bg-green-500 text-white text-base font-medium rounded-md w-full shadow-sm hover:bg-green-700 focus:outline-none focus:ring-2 focus:ring-green-300">
          OK
        </button>
      </div>
    </div>
  </div>
</div>
```

### Form Layout

```html
<div class="w-full max-w-md mx-auto">
  <form class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4">
    <div class="mb-4">
      <label class="block text-gray-700 text-sm font-bold mb-2" for="username">
        Username
      </label>
      <input class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline" id="username" type="text" placeholder="Username">
    </div>
    <div class="mb-6">
      <label class="block text-gray-700 text-sm font-bold mb-2" for="password">
        Password
      </label>
      <input class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:shadow-outline" id="password" type="password" placeholder="******************">
      <p class="text-red-500 text-xs italic">Please choose a password.</p>
    </div>
    <div class="flex items-center justify-between">
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline" type="button">
        Sign In
      </button>
      <a class="inline-block align-baseline font-bold text-sm text-blue-500 hover:text-blue-800" href="#">
        Forgot Password?
      </a>
    </div>
  </form>
</div>
```

## Performance Optimization

Tailwind can generate large CSS files if not properly optimized. Here's how to optimize performance:

### PurgeCSS Integration

Tailwind v3.0+ automatically removes unused CSS with its built-in PurgeCSS integration. Configure the `content` option to include all files containing class names:

```javascript
// tailwind.config.js
module.exports = {
  content: [
    './src/**/*.{html,js,jsx,ts,tsx,vue}',
  ],
  // ...
}
```

### Just-in-Time (JIT) Mode

Tailwind v3.0+ uses JIT mode by default, which:
- Only generates the CSS you're actually using
- Provides faster build times
- Allows for on-demand generation of variants
- Enables arbitrary values (e.g., `text-[16px]`, `bg-[#bada55]`)

### Minification

Use a minifier like CSSNano in your build process:

```javascript
// postcss.config.js
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
    ...(process.env.NODE_ENV === 'production' ? { cssnano: {} } : {})
  }
}
```

### Splitting Configuration

For large projects, consider splitting your configuration:

```javascript
// tailwind.config.js
const colors = require('./tailwind/colors')
const spacing = require('./tailwind/spacing')
const typography = require('./tailwind/typography')

module.exports = {
  content: ['./src/**/*.{html,js}'],
  theme: {
    colors,
    spacing,
    extend: {
      typography,
    },
  },
  // ...
}
```

## Best Practices

### Component-First Approach

While Tailwind is utility-first, for maintainable code:
1. Start with utilities for rapid prototyping
2. Identify repeated patterns
3. Extract components using `@apply` or component frameworks
4. Maintain a consistent design system

### Naming Conventions

For custom components and utilities:
- Use kebab-case for class names: `btn-primary`, not `btnPrimary`
- Use descriptive, purpose-oriented names: `card-title` instead of `large-bold-text`
- Namespace custom utilities: `custom-text-shadow` instead of just `text-shadow`

### File Organization

Structure your CSS files:

```
src/
├── css/
│   ├── main.css             # Import directives and global styles
│   ├── components/          # Component styles using @apply
│   │   ├── buttons.css
│   │   ├── cards.css
│   │   └── forms.css
│   └── utilities/           # Custom utilities
│       ├── text.css
│       └── animations.css
```

### Responsive Design Tips

1. Design for mobile first, then expand to larger screens
2. Use consistent breakpoints throughout your application
3. Don't overuse responsive prefixes; group similar responsive behaviors together
4. Test on actual devices, not just browser resizing

### Accessibility Considerations

1. Maintain sufficient color contrast (4.5:1 minimum)
2. Use semantic HTML elements
3. Ensure focus states are visible: `focus:ring focus:ring-blue-300`
4. Provide appropriate text alternatives for non-text content
5. Test with screen readers and keyboard navigation

### Common Pitfalls to Avoid

1. **Class Name Soup**: Avoid extremely long strings of utility classes. Extract to components when it becomes unwieldy.
2. **Inconsistent Designs**: Create a design system and stick to it.
3. **Specificity Issues**: Be cautious when mixing Tailwind with custom CSS.
4. **Over-customization**: Don't modify the default configuration too early.
5. **Neglecting Dark Mode**: Design for both light and dark themes from the start.

## Resources

- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [Tailwind CSS Color Palette](https://tailwindcss.com/docs/customizing-colors)
- [Tailwind CSS Typography](https://tailwindcss.com/docs/typography-plugin)

---

<footer>
  <p style="text-align: center; font-size: 0.9rem; color: gray;">Prepared by Team Nexus</p>
</footer>
