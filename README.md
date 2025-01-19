# Documented Next.js Learning Progress

## Table of Contents

- [Day 1 (Jan 04)](#day-1-jan-19)
  - [Chapter 1: Getting Started!](#chapter-1-getting-started)
  - [Chapter 2: CSS Styling!](#chapter-2-css-styling)
  - [Chapter 3: Optimizing Fonts and Images!](#chapter-3-optimizing-fonts-and-images)
  - 

---

## Day 1 (Jan 19)

### Chapter 1: Getting Started!
- **Introduction to Next.js**: 
Next.js is a popular React-based framework for building server-side rendered (SSR) and statically generated websites and applications.

- **Setting up a new project**:  
I set up a new project using:
```bash
npx create-next-app my-app
```
and ran it with:
```bash
pnpm dev
```
to see the default Next.js page. I also explored the project structure and the different folders and files created by the CLI.

- **Understanding the file system**:  
I learned about the different types of files and folders in a Next.js project, including:
- **pages**: Contains route files for the application.
- **components**: Contains reusable UI components.
- **public**: Used for static assets like images.
- **styles**: Contains CSS files for styling the app.

Additionally, I learned about the `next.config.js` file and how it can be used to configure the project.

### Prerequisites
- Node.js (version 14 or higher)
- npm or yarn installed on your machine

## Chapter 2: CSS Styling

### CSS in Next.js
Next.js supports various ways to style your application, including CSS Modules, global CSS, and utility-first frameworks like Tailwind CSS.

### CSS Modules
- **Scoped Styling**: CSS Modules allow writing styles scoped to specific components to prevent style conflicts.
- **Usage**: Styles are imported as modules, and class names are applied dynamically.

Example:
```javascript
import styles from './Button.module.css';

function Button() {
  return <button className={styles.button}>Click Me</button>;
}
```

### Global CSS
- **Application-Wide Styles**: Global CSS is used for styles that apply to the entire app.
- **Configuration**: Add a `global.css` file in the `styles` directory and import it in `_app.js`.

Example:
```javascript
import '../styles/global.css';
```

### Tailwind CSS
- **Utility-First Framework**: Tailwind CSS provides a wide range of utility classes for quick styling.
- **Configuration**: The `tailwind.config.js` file allows customization of styles and themes.

To install Tailwind CSS:
```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init
```

## Chapter 3: Optimizing Fonts and Images

### Font Optimization
- **Efficient Loading**: Next.js optimizes font loading to reduce layout shifts and improve performance.
- **Font Display**: The `font-display` property ensures smooth font loading behavior.
- **Google Fonts Integration**: Fonts like Inter can be imported directly using `next/font/google`.

Example:
```javascript
import { Inter } from 'next/font/google';
const inter = Inter({ subsets: ['latin'] });
```

### Image Optimization
- **Next.js Image Component**: The `next/image` component optimizes images automatically.
- **Features**: Lazy loading, responsive sizes, and support for modern formats like WebP.

Example:
```javascript
import Image from 'next/image';

function MyImage() {
  return <Image src="/example.jpg" alt="Example" width={500} height={300} />;
}
```

### Lazy Loading
- **On-Demand Resource Loading**: Images and other resources load only when they are needed, improving performance.
- **Implementation**: By default, the `next/image` component enables lazy loading.

---