# Portfolio Frontend - React Application

A modern, responsive React frontend for a personal portfolio website with smooth animations and dynamic content powered by Sanity CMS.

## 🎯 Overview

This is the frontend application built with React, featuring a beautiful UI with smooth animations using Framer Motion and dynamic content management through Sanity CMS integration.

## ✨ Features

-   🎨 **Modern UI/UX** - Clean, professional design with SCSS styling
-   ⚡ **Smooth Animations** - Powered by Framer Motion
-   📱 **Fully Responsive** - Works seamlessly on all devices
-   🔄 **Dynamic Content** - Real-time updates from Sanity CMS
-   🚀 **Performance Optimized** - Fast load times and smooth interactions
-   🎯 **Interactive Sections**:
    -   Hero/Header with navigation
    -   About section
    -   Skills showcase
    -   Portfolio/Work projects
    -   Testimonials
    -   Contact form with footer

## 🛠️ Tech Stack

-   **React 18** - UI library
-   **SCSS/Sass** - Styling with variables and mixins
-   **Framer Motion** - Animation library
-   **Sanity Client** - CMS integration
-   **React Icons** - Icon library
-   **React Tooltip** - Interactive tooltips

## 📁 Project Structure

```
frontend_react/
├── src/
│   ├── App.js                # Main app component
│   ├── App.scss              # Global styles
│   ├── index.js              # Entry point
│   ├── client.js             # Sanity client config
│   │
│   ├── assets/               # Images and static files
│   │
│   ├── components/           # Reusable components
│   │   ├── NavigationDots.jsx
│   │   ├── SocialMedia.jsx
│   │   └── Navbar/
│   │       ├── Navbar.jsx
│   │       └── Navbar.scss
│   │
│   ├── container/            # Page sections
│   │   ├── About/
│   │   ├── Footer/
│   │   ├── Header/
│   │   ├── Skills/
│   │   ├── Testimonial/
│   │   └── Work/
│   │
│   ├── constants/            # Constants and configs
│   │   └── images.js
│   │
│   └── wrapper/              # HOC wrappers
│       ├── AppWrap.js
│       └── MotionWrap.js
│
├── public/                   # Static public assets
│   ├── index.html
│   ├── manifest.json
│   └── robots.txt
│
└── build/                    # Production build (generated)
```

## 🚀 Getting Started

### Prerequisites

-   Node.js (v14 or higher)
-   npm or yarn
-   Sanity backend running (see backend_sanity README)

### Installation

1. **Install dependencies**

    ```bash
    npm install
    ```

2. **Set up environment variables**

    Create a `.env` file in the root directory:

    ```env
    REACT_APP_SANITY_PROJECT_ID=your_project_id
    REACT_APP_SANITY_TOKEN=your_token
    ```

3. **Start development server**
    ```bash
    npm start
    ```
    Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

## 📜 Available Scripts

### `npm start`

Runs the app in development mode.\
The page will reload when you make changes.

### `npm test`

Launches the test runner in interactive watch mode.

### `npm run build`

Builds the app for production to the `build` folder.\
Optimizes the build for best performance.

### `npm run eject`

**Note: This is a one-way operation!**\
Ejects from Create React App for full configuration control.

## 🎨 Styling

The project uses **SCSS** for styling:

-   Global styles in `App.scss`
-   Component-specific styles in component folders
-   CSS variables for consistent theming
-   Responsive breakpoints for mobile-first design

### Key Style Features

-   Custom color palette
-   Smooth transitions
-   Responsive grid layouts
-   Mobile-first approach

## 🔌 Sanity Integration

### Client Configuration (`client.js`)

```javascript
import sanityClient from '@sanity/client';
import imageUrlBuilder from '@sanity/image-url';

export const client = sanityClient({
    projectId: process.env.REACT_APP_SANITY_PROJECT_ID,
    dataset: 'production',
    apiVersion: '2022-02-01',
    useCdn: true,
    token: process.env.REACT_APP_SANITY_TOKEN,
});

const builder = imageUrlBuilder(client);
export const urlFor = (source) => builder.image(source);
```

### Fetching Data

```javascript
import { client } from './client';

// Fetch all works
client.fetch('*[_type == "works"]').then((data) => console.log(data));
```

## 🎭 Components

### Higher-Order Components (HOC)

-   **AppWrap**: Wraps sections with common layout elements
-   **MotionWrap**: Adds animation capabilities to sections

### Reusable Components

-   **Navbar**: Main navigation with responsive menu
-   **NavigationDots**: Section navigation indicators
-   **SocialMedia**: Social media links sidebar

### Container Components

Each section (About, Skills, Work, etc.) is a self-contained component with its own logic and styling.

## 📱 Responsive Design

Breakpoints:

-   Mobile: `< 768px`
-   Tablet: `768px - 1024px`
-   Desktop: `> 1024px`

## 🚀 Deployment

### Build for Production

```bash
npm run build
```

### Deploy Options

**Vercel** (Recommended)

```bash
npm install -g vercel
vercel
```

**Netlify**

```bash
npm install -g netlify-cli
netlify deploy --prod --dir=build
```

**GitHub Pages**

```bash
npm install --save-dev gh-pages
# Add to package.json: "homepage": "https://yourusername.github.io/portfolio"
npm run deploy
```

## 🔧 Environment Variables

Required variables:

```env
REACT_APP_SANITY_PROJECT_ID=your_sanity_project_id
REACT_APP_SANITY_TOKEN=your_sanity_token (optional, for private content)
```

## 🎯 Optimization

-   Code splitting for better performance
-   Lazy loading of images
-   Optimized animations
-   Minified production build
-   CDN-ready static assets

## 🐛 Troubleshooting

### Common Issues

**SCSS compilation errors**

```bash
npm install node-sass --save-dev
```

**Sanity connection issues**

-   Check your project ID and token
-   Verify CORS settings in Sanity dashboard
-   Ensure backend is running

## 📚 Learn More

-   [React Documentation](https://reactjs.org/)
-   [Create React App Documentation](https://create-react-app.dev/)
-   [Framer Motion](https://www.framer.com/motion/)
-   [Sanity.io](https://www.sanity.io/docs)
-   [SCSS Guide](https://sass-lang.com/guide)

## 👤 Author

-   GitHub: [@audrbar](https://github.com/audrbar)

## 📄 License

This project is private and not licensed for public use.

## 🤝 Contributing

This is a personal portfolio project. Feel free to use it as inspiration for your own portfolio!

## Acknowledgements

-   [**JavaScript Mastery** Build and Deploy a Fullstack Responsive Portfolio Website](https://www.youtube.com/watch?v=3HNyXCPDQ7Q&t=373s)

---

**Built with Create React App** | **Powered by Sanity CMS**
