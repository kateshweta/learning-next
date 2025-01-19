# Next.js Dashboard App

This project is based on the [Next.js Dashboard App tutorial](https://nextjs.org/learn/dashboard-app/getting-started). It serves as a learning project to understand and implement Next.js features for building modern web applications.

## Table of Contents
- [Chapter 1: Getting Started](#chapter-1-getting-started)
- [Chapter 2: CSS Styling](#chapter-2-css-styling)
- [Chapter 3: Optimizing Fonts and Images](#chapter-3-optimizing-fonts-and-images)
- [Chapter 4: Creating Layouts and Pages](#chapter-4-creating-layouts-and-pages)
- [Chapter 5: Navigating Between Pages](#chapter-5-navigating-between-pages)

## Chapter 1: Getting Started

### Introduction to Next.js
Next.js is a popular React-based framework for building server-side rendered (SSR) and statically generated websites and applications.

### Setting up a New Project
I set up a new project using:
```bash
npx create-next-app my-app
```
and ran it with:
```bash
pnpm dev
```
to see the default Next.js page. I also explored the project structure and the different folders and files created by the CLI.

### Understanding the File System
I learned about the different types of files and folders in a Next.js project, including:
- **pages**: Contains route files for the application.
- **components**: Contains reusable UI components.
- **public**: Used for static assets like images.
- **styles**: Contains CSS files for styling the app.

Additionally, I learned about the `next.config.js` file and how it can be used to configure the project.

## Chapter 2: CSS Styling

### CSS in Next.js
Next.js supports various ways to style your application, including CSS Modules, global CSS, and utility-first frameworks like Tailwind CSS.

### CSS Modules
- **Scoped Styling**: CSS Modules allow writing styles scoped to specific components to prevent style conflicts.
- **Usage**: Styles are imported as modules, and class names are applied dynamically.

### Global CSS
- **Application-Wide Styles**: Global CSS is used for styles that apply to the entire app.
- **Configuration**: Add a `global.css` file in the `styles` directory and import it in `_app.js`.

### Tailwind CSS
- **Utility-First Framework**: Tailwind CSS provides a wide range of utility classes for quick styling.
- **Configuration**: The `tailwind.config.js` file allows customization of styles and themes.

## Chapter 3: Optimizing Fonts and Images

### Font Optimization
- **Efficient Loading**: Next.js optimizes font loading to reduce layout shifts and improve performance.
- **Font Display**: The `font-display` property ensures smooth font loading behavior.
- **Google Fonts Integration**: Fonts like Inter can be imported directly using `next/font/google`.

### Image Optimization
- **Next.js Image Component**: The `next/image` component optimizes images automatically.
- **Features**: Lazy loading, responsive sizes, and support for modern formats like WebP.

### Lazy Loading
- **On-Demand Resource Loading**: Images and other resources load only when they are needed, improving performance.

## Chapter 4: Creating Layouts and Pages

### Nested Routing
Next.js uses file-system routing where folders represent route segments that map to URL segments. Nested routes are created by nesting folders and adding `page.tsx` files inside them.

### Dashboard Pages
- **Creating Routes**: New routes can be added by creating folders inside `/app` and adding `page.tsx` files.
  - `/dashboard/page.tsx`: Accessible at `/dashboard`.
  - `/dashboard/customers/page.tsx`: Accessible at `/dashboard/customers`.
  - `/dashboard/invoices/page.tsx`: Accessible at `/dashboard/invoices`.

### Creating Shared Layouts
Dashboards often share a common layout, such as navigation bars. In Next.js, you can use a `layout.tsx` file to define a shared layout for multiple pages.

### Root Layout
The `layout.tsx` file in `/app` is the root layout of the application and is required in every Next.js app. It defines global structures like `<html>` and `<body>` tags and includes global styles and metadata.

### Benefits of Layouts
- **Partial Rendering**: Layout components don’t re-render when navigating between child pages, preserving React state.
- **Code Colocation**: UI components, tests, and other files can be colocated with their routes, keeping the project organized.

## Chapter 5: Navigating Between Pages

### Client-Side Navigation
- **Efficient Transitions**: Next.js uses the `next/link` component for seamless client-side navigation between pages.
- **Example**:
```jsx
import Link from 'next/link';

export default function Home() {
  return (
    <nav>
      <Link href="/about">About</Link>
      <Link href="/contact">Contact</Link>
    </nav>
  );
}
```

### Prefetching
- **Optimized Navigation**: By default, Next.js prefetches linked pages in the background, speeding up navigation.

### Dynamic Routing
- **URL Parameters**: Use brackets (`[param]`) in file names to create dynamic routes.
- **Example**:
  - `/post/[id].tsx`: Accessible at `/post/1`, `/post/2`, etc.

### API Routes
- **Custom API Endpoints**: Define server-side logic using API routes in the `/pages/api` directory.
- **Example**:
```javascript
export default function handler(req, res) {
  res.status(200).json({ message: "Hello, API!" });
}
```

This chapter explained how to navigate between pages, utilize dynamic routing, and leverage Next.js features for creating efficient and user-friendly navigation experiences.
