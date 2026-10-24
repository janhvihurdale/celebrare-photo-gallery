# 📸 Photo Gallery Web App

A modern, responsive photo gallery application built with React and Vite that allows users to browse, search, and manage their favorite photos.

## Overview

This is a beautiful and interactive photo gallery web application that fetches photos from the Picsum Photos API. Users can search photos by author, toggle favorites, and persistent storage keeps track of their favorite photos across sessions.

## ✨ Features

- **Photo Gallery Display**: Browse a grid of 30 high-quality photos with lazy loading
- **Search Functionality**: Filter photos by author name in real-time
- **Favorites Management**: Toggle photos as favorites with persistent storage
- **Responsive Design**: Mobile-first responsive layout using Tailwind CSS
- **Smooth Animations**: Hover effects and transitions for better UX
- **Error Handling**: Graceful error messages and retry functionality
- **Loading States**: Beautiful loading spinner while fetching photos
- **Favorites Counter**: Footer displays current favorite count

## 🛠️ Tech Stack

- **Frontend Framework**: React 19.2.6
- **Build Tool**: Vite 8.0.12
- **Styling**: Tailwind CSS 4.3.0
- **Package Manager**: npm
- **Linting**: ESLint 10.3.0

## 📁 Project Structure

```
photo_gallery_web_app/
├── src/
│   ├── components/
│   │   └── PhotoCard.jsx          # Individual photo card component
│   ├── hooks/
│   │   └── useFetchPhotos.js      # Custom hook for fetching photos from API
│   ├── reducers/
│   │   └── favouritesReducer.js   # State reducer for favorites management
│   ├── assets/                    # Static assets (images, SVGs)
│   ├── App.jsx                    # Main application component
│   ├── App.css                    # Application styles
│   ├── index.css                  # Global styles
│   └── main.jsx                   # React DOM entry point
├── public/
│   ├── favicon.svg
│   └── icons.svg
├── index.html                     # HTML template
├── package.json                   # Project dependencies
├── vite.config.js                 # Vite configuration
├── eslint.config.js               # ESLint configuration
└── README.md                      # This file
```

## 🚀 Getting Started

### Prerequisites

- Node.js (v14 or higher)
- npm (v6 or higher)

### Installation

1. **Clone or navigate to the project directory**:
   ```bash
   cd photo_gallery_web_app
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

### Development

Start the development server:

```bash
npm run dev
```

The application will be available at `http://localhost:5173` (or the port shown in your terminal).

### Build

Create a production build:

```bash
npm run build
```

The optimized build files will be in the `dist/` directory.

### Preview

Preview the production build locally:

```bash
npm run preview
```

### Linting

Run ESLint to check code quality:

```bash
npm run lint
```

## 📝 Component Structure

### App.jsx (Main Component)

The main application component that orchestrates the entire photo gallery:

- Manages global state using `useReducer` for favorites
- Handles search functionality
- Manages loading and error states
- Displays the header with search input
- Renders the photo gallery grid
- Shows the favorites counter footer

**Key Features**:
- Real-time search filtering by author name
- Loading and error state handling
- Favorites initialization from localStorage on component mount

### PhotoCard.jsx

Reusable component that displays individual photo cards:

- Shows photo image with author name
- Heart icon button to toggle favorites
- Lazy loading for images
- Hover scale animation effect
- Accessible ARIA labels

### useFetchPhotos Hook

Custom React hook for fetching photos from the Picsum Photos API:

- Fetches a configurable number of photos (default: 30)
- Manages loading and error states
- Maps API response to include `isFavourite` flag
- Returns photos, loading state, and error messages

**API Used**: [Picsum Photos API](https://picsum.photos/)

### favouritesReducer.js

State management reducer and helpers for managing favorites:

**Actions**:
- `TOGGLE_FAVOURITE`: Toggle favorite status for a photo and persist to localStorage
- `SET_FAVOURITES_FROM_STORAGE`: Initialize state from localStorage

**Helper Functions**:
- `loadInitialFavourites(fetchedPhotos)`: Loads saved favorites from localStorage and merges with current photos

**Persistence**: All favorites are automatically saved to localStorage and restored on app reload.

## 🎨 Styling

The application uses **Tailwind CSS** for styling with:

- Responsive grid layout (1 column on mobile, 2 on tablet, 4 on desktop)
- Smooth transitions and hover effects
- Clean, modern color scheme
- Accessible focus states
- Mobile-first responsive design

## 💾 Data Persistence

Favorite photos are automatically saved to the browser's localStorage under the key `'favourites'`. This allows users to:

- Keep their favorite photos across browser sessions
- Have their preferences persisted even after closing the browser
- See updated favorites on page reload

## 🔧 API Integration

The application fetches photos from the **Picsum Photos API**:

```
https://picsum.photos/v2/list?limit=30
```

Each photo object contains:
- `id`: Unique identifier
- `author`: Photographer name
- `download_url`: Photo image URL
- `isFavourite`: Custom flag for tracking favorites

## 📱 Responsive Breakpoints

- **Mobile**: 1 column layout
- **Tablet (sm)**: 2 column layout
- **Desktop (lg)**: 4 column layout

## ⚡ Performance Features

- **Lazy Loading**: Images use native lazy loading
- **Image Optimization**: Images are requested with specific dimensions (`?w=400&h=300&fit=crop`)
- **useCallback**: Optimized event handlers to prevent unnecessary re-renders
- **useMemo**: Memoized filtered photos to prevent expensive recalculations
- **Code Splitting**: Vite automatically handles code splitting

## 🐛 Error Handling

- Network errors are caught and displayed to users
- Retry button available in error state
- Fallback messages for edge cases (no photos found, search matches)

## 📦 Dependencies

### Production
- `react` - UI library
- `react-dom` - React DOM rendering
- `tailwindcss` - Utility-first CSS framework
- `@tailwindcss/vite` - Tailwind CSS Vite plugin

### Development
- `vite` - Next generation frontend tooling
- `@vitejs/plugin-react` - React plugin for Vite
- `eslint` - Code quality tool
- `@types/react` - TypeScript types for React
- `@types/react-dom` - TypeScript types for React DOM

## 🔍 Usage Examples

### Search by Author

Type an author's name in the search box to filter photos:
- Search is case-insensitive
- Results update in real-time
- Empty search shows all photos

### Toggle Favorites

Click the heart icon on any photo card to:
- Add/remove from favorites
- See the counter update in the footer
- Persist selection across sessions

## 🎯 Future Enhancements

Potential features to add:
- Photo details modal with full-size image
- Sort options (newest, oldest, alphabetical)
- Filter by photo dimensions
- Share/download photo functionality
- User authentication for cloud sync
- Photo categories/collections
- Ratings and comments

## 🤝 Contributing

To contribute to this project:

1. Make your changes
2. Run `npm run lint` to check code quality
3. Test the application with `npm run dev`
4. Submit your changes

## 📄 License

This project is open source and available for personal and educational use.

## 🙏 Acknowledgments

- [Picsum Photos](https://picsum.photos/) - Free photo API service
- [React](https://react.dev/) - UI library
- [Tailwind CSS](https://tailwindcss.com/) - CSS framework
- [Vite](https://vitejs.dev/) - Build tool and dev server

## 📞 Support

For issues, questions, or suggestions, please feel free to open an issue or contact the development team.

---

**Built with ❤️ using React, Vite, and Tailwind CSS**
