# Markdown Note App (React + TypeScript + Vite)

A minimal note-taking app with:
- Create, edit, delete notes
- Markdown support (preview via React components)
- Tagging and filtering
- Persistent storage via localStorage
- Type-safe components with React + TypeScript
- Fast dev setup using Vite

## Tech Stack
- React 18 + TypeScript
- Vite
- CSS Modules
- ESLint (flat config)
- localStorage for persistence

## Getting Started

### Prerequisites
- Node.js 18+ (recommend LTS)

### Install
```bash
npm install
```

### Run Dev Server
```bash
npm run dev
```
Then open the shown URL (usually http://localhost:5173).

### Build
```bash
npm run build
```

### Preview Production Build
```bash
npm run preview
```

## Scripts (package.json)
- dev: Start Vite dev server
- build: Type-check + build for production
- preview: Preview built app
- lint: Run ESLint

## Project Structure
```text
src/
  main.tsx         # App entry
  App.tsx          # Root layout & routing logic (if added)
  NoteList.tsx     # List + tag filtering
  Note.tsx         # View a single note
  NewNote.tsx      # Create note page
  EditNote.tsx     # Edit note page
  NoteForm.tsx     # Shared form component
  NoteLayout.tsx   # Layout wrapper for routes with :id
  useLocalStorage.ts # Custom hook for persistence
  assets/          # Static assets
  *.module.css     # Scoped styles
```

## Data Model (Conceptual)
```ts
type Tag = { id: string; label: string };
type NoteData = { title: string; markdown: string; tagIds: string[] };
type Note = NoteData & { id: string };
```
Notes and tags are stored in localStorage as arrays. Derivations (like resolving tagIds to Tag objects) happen in components/selectors.

## Custom Hook: useLocalStorage
A small abstraction over useState that:
- Initializes from localStorage
- Persists on change
- Namespaces by key

## Possible Improvements
- Search across title + body
- Drag-and-drop note ordering
- Export / import notes (JSON)
- Markdown toolbar
- Dark mode
- Sync (Supabase / Firebase)
- Unit tests (React Testing Library + Vitest)

## FAQ
Q: Why localStorage?  
A: Zero backend, instant persistence.

Q: How to reset all notes?  
A: Clear site data in browser dev tools or remove relevant localStorage keys.

---

Feel free to adjust naming or add screenshots