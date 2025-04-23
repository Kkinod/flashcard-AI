# Educational Flashcards

## 1. Project Name

Educational Flashcards

## 2. Project Description

Educational Flashcards is a web-based application that allows users to create, manage, and review flashcards for effective learning using spaced repetition. The app provides two main approaches for flashcard creation:

- **AI-Driven Flashcard Generation:** Automatically generates flashcards from provided text, enforcing character limits (front: max 200 characters, back: max 500 characters) and including metadata such as creation date and user details.
- **Manual Flashcard Creation:** Offers a simple form for users to manually create flashcards with built-in validation.

Users can review generated flashcard candidates by accepting, editing, or rejecting them (individually or in bulk). The application also features secure user account management, including registration, login, password updates, and account deletion. Integration with an open-source spaced repetition algorithm further enhances the learning process.

## 3. Tech Stack

**Frontend:**

- [Astro](https://astro.build/) v5.5.5 - Modern web framework for building fast, content-focused websites
- [React](https://react.dev/) v19.0.0 - UI library for building interactive components
- [TypeScript](https://www.typescriptlang.org/) v5 - Type-safe JavaScript
- [Tailwind CSS](https://tailwindcss.com/) v4.0.17 - Utility-first CSS framework
- [Shadcn/ui](https://ui.shadcn.com/) - for accessible React components

**Backend:**

- Supabase: Provides a PostgreSQL database, authentication, and backend-as-a-service

**AI Integration:**

- Openrouter.ai: Access to multiple AI models (e.g., OpenAI, Anthropic, Google) for flashcard generation

**CI/CD & Hosting:**

- GitHub Actions for continuous integration and deployment
- DigitalOcean for hosting via Docker images

**Other:**

- Conventional Commits for version control

## 4. Getting Started Locally

### Prerequisites

- Node.js version specified in `.nvmrc`: **22.14.0**
- A package manager: pnpm (recommended) or npm

### Installation Steps

1. Clone the repository:
   ```bash
   git clone https://github.com/Kkinod/flashcard-AI.git

   ```
2. Navigate to the project directory:
   ```bash
    cd 10xDevs-Fiszki
   ```
3. Install dependencies:
   ```bash
   npm install
   ```
4. Start the development server:
   ```bash
   npm run dev
   ```
5. Open [http://localhost:3000](http://localhost:3000) in your browser to view the app.

## 5. Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run lint` - Run ESLint
- `npm run lint:fix` - Fix ESLint issues

## 6. Project Structure

```md
.
├── src/
│   ├── layouts/    # Astro layouts
│   ├── pages/      # Astro pages
│   │   └── api/    # API endpoints
│   ├── components/ # UI components (Astro & React)
│   └── assets/     # Static assets
├── public/         # Public assets
```

## 7. Project Status

The project is currently in its Minimum Viable Product (MVP) stage, focusing on a web-based solution. Future iterations may include additional features and a mobile version.

## 8. Cursor IDE

The project includes AI rules in `.cursor/rules/` directory that help Cursor IDE understand the project structure and provide better code suggestions.

## 9. License

This project is licensed under the MIT License.
