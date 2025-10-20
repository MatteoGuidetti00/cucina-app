# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a standalone single-page React application for kitchen and diet management (Gestionale Cucina & Dieta). The entire application is contained in a single `index.html` file that uses browser-based React (via CDN), making it immediately usable without any build process.

**Key Features:**
- Recipe management with ingredients and nutritional macros
- Ingredient inventory tracking
- Shopping list generation (manual or auto-generated from recipes)
- Meal tracking with daily macro totals
- Data import/export (JSON backup)
- Random recipe suggestion based on available inventory

## Architecture

### Single-File Structure
The application uses an all-in-one HTML file approach:
- **HTML scaffold**: Basic page structure with root div
- **External dependencies**: React 18, ReactDOM, Babel Standalone, Tailwind CSS (all via CDN)
- **Embedded React app**: JSX code in a `<script type="text/babel">` block
- **Inline SVG icons**: Custom icon components (Plus, Trash2, ShoppingCart, etc.)

### State Management
The app uses React hooks exclusively:
- `useState` for all application state (ricette, inventario, listaSpesa, pasti, editingId, activeTab)
- `useEffect` for localStorage persistence (auto-save on state changes, auto-load on mount)
- No external state management library

### Data Flow
1. **localStorage key**: All data stored under `cucinaAppData` as a single JSON object
2. **Data structure**: `{ ricette, inventario, listaSpesa, pasti }`
3. **Each entity uses**: unique `id` (timestamp-based), `nome`, `quantita`, `unita`
4. **Recipes include**: `ingredienti` array, `istruzioni` string, `macro` object (calorie, proteine, carboidrati, grassi)
5. **Meals include**: `data` field for date tracking

### Component Organization
The `CucinaApp` component handles everything with conditional rendering based on `activeTab`:
- **ricette**: Recipe list and creation form
- **inventario**: Ingredient inventory with inline editing
- **spesa**: Shopping list with checkbox completion tracking
- **tracking**: Meal logging with daily macro totals

### Key Functions
- `aggiungiRicetta()` / `eliminaRicetta()`: Manage recipes
- `aggiungiInventario()` / `eliminaInventario()` / `modificaInventario()`: Manage inventory with inline editing
- `aggiungiSpesa()` / `eliminaSpesa()` / `toggleComprato()`: Shopping list management
- `generaListaSpesaDaRicetta()`: Automatically adds missing ingredients to shopping list
- `ricettaRandom()`: Suggests a recipe based on available inventory ingredients
- `aggiungiPasto()` / `eliminaPasto()`: Track meals
- `totaliGiornalieri()`: Calculate daily macro totals for a specific date
- `usaRicetta()`: Quick-add recipe to meal tracking
- `esportaDati()` / `importaDati()`: JSON backup/restore functionality

## Development Workflow

### No Build System Required
Simply open `index.html` in any modern browser. Changes take effect immediately on page refresh.

### Testing Changes
1. Open `index.html` in Chrome/Firefox/Edge
2. Edit the file
3. Refresh browser (Ctrl+R / Cmd+R)
4. Check browser console (F12) for any errors

### Data Persistence
All data is stored in browser localStorage. To preserve data during development:
- Use Export feature to backup before major changes
- Check localStorage in DevTools: Application → Local Storage → file:// → `cucinaAppData`

## Common Modifications

### Adding New Fields
1. Update initial state in `useState` declarations
2. Add form inputs in the relevant tab section
3. Update the corresponding `aggiungi*` function to include new fields
4. Modify display/render logic in the list items

### Adding New Icons
Define new SVG components following the existing pattern (20x20 viewBox, currentColor stroke).

### Styling Changes
Use Tailwind CSS utility classes directly in className attributes. The Tailwind CDN provides all standard utilities.

### Adding New Tabs
1. Add tab name to the map in the tab navigation (line ~362)
2. Add corresponding conditional rendering block in the main content area
3. Add necessary state and functions

## Deployment Options

### Local Use
Open `index.html` directly in browser. Data persists per-device in localStorage.

### GitHub Pages (as described in README.md)
```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/USERNAME/cucina-app.git
git branch -M main
git push -u origin main
```
Then enable GitHub Pages in repository settings: Settings → Pages → Source: main branch → Save

### Adding Cloud Sync
To add Firebase or similar cloud database, you would need to:
1. Add Firebase SDK via CDN
2. Replace localStorage calls with Firestore operations
3. Add authentication system
4. Update useEffect hooks for real-time sync

## Important Notes

- **No package.json**: This project intentionally has no Node.js dependencies
- **No build process**: Everything runs directly in the browser
- **Case-sensitive matching**: Ingredient matching uses `toLowerCase()` for comparison
- **ID generation**: Uses `Date.now()` or `Date.now() + Math.random()` for unique IDs
- **Italian language**: UI text is in Italian per original requirements
- **Unit measures**: Defined in `unitaMisura` array (g, kg, ml, l, cucchiaio, cucchiaino, tazza, pz, fetta, spicchio)
