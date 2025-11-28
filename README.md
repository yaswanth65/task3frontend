# TaskFlow Frontend

A modern, responsive React + TypeScript + Vite SPA for task management and team collaboration. Features real-time updates via WebSocket, Kanban board, calendar view, and messaging.

## 🚀 Live Deployment

**Frontend App:** https://task3frontend.vercel.app

**Login Page:** https://task3frontend.vercel.app/login

---

## 📋 Features

- ✅ User authentication & registration
- ✅ Responsive dashboard
- ✅ Kanban board for task management
- ✅ Calendar view for deadlines
- ✅ Task creation, editing, deletion
- ✅ Real-time messaging system
- ✅ Team collaboration
- ✅ User settings & profile
- ✅ Report analytics
- ✅ Dark/Light mode support (Tailwind)
- ✅ Offline-ready with Vite
- ✅ Cross-browser compatible

---

## 🛠️ Tech Stack

- **Framework:** React 18+ with TypeScript
- **Build Tool:** Vite
- **Styling:** Tailwind CSS + PostCSS
- **State Management:** Zustand
- **HTTP Client:** Axios
- **Real-time:** Socket.IO client
- **UI Components:** Custom built
- **Icons:** Lucide icons
- **Date Handling:** date-fns
- **Calendar:** React Calendar

---

## 📦 Project Structure

```
src/
├── main.tsx                 # Application entry point
├── App.tsx                  # Root component
├── vite-env.d.ts           # Vite env types
├── index.css               # Global styles
├── components/
│   ├── Layout.tsx          # Main layout wrapper
│   ├── OnboardingOverlay.tsx # First-time user guide
│   ├── ui/                 # Reusable UI components
│   │   ├── Button.tsx
│   │   ├── Input.tsx
│   │   ├── Modal.tsx
│   │   ├── Badge.tsx
│   │   ├── Avatar.tsx
│   │   └── LoadingSpinner.tsx
│   └── tasks/              # Task-related components
│       ├── KanbanBoard.tsx # Kanban board view
│       ├── TaskCard.tsx    # Task card component
│       ├── CreateTaskModal.tsx
│       └── EditTaskModal.tsx
├── pages/                  # Page components
│   ├── LoginPage.tsx
│   ├── RegisterPage.tsx
│   ├── DashboardPage.tsx
│   ├── TasksPage.tsx
│   ├── CalendarPage.tsx
│   ├── MessagesPage.tsx
│   ├── TeamPage.tsx
│   ├── ReportsPage.tsx
│   └── SettingsPage.tsx
├── lib/                    # Utilities & APIs
│   ├── api.ts              # Axios instance & API calls
│   ├── socket.ts           # WebSocket configuration
│   └── utils.ts            # Helper functions
├── stores/                 # Zustand stores
│   ├── authStore.ts        # Authentication state
│   ├── taskStore.ts        # Tasks state
│   └── messageStore.ts     # Messages state
└── public/                 # Static assets
```

---

## 🚀 Getting Started

### Prerequisites

- Node.js v16 or higher
- npm or yarn
- Backend API running (see backend README)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yaswanth65/task3frontend.git
   cd task3frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Create `.env.local` file** (optional - uses production backend by default)
   ```env
   VITE_API_URL=http://localhost:5000/api
   VITE_WS_URL=http://localhost:5000
   ```

4. **Run development server**
   ```bash
   npm run dev
   ```

   App runs on `http://localhost:5173`

### Available Scripts

```bash
npm run dev         # Start development server with HMR
npm run build       # Build for production
npm run preview     # Preview production build locally
npm run lint        # Run ESLint
npm run type-check  # Check TypeScript types
```

---

## 🔐 Environment Variables

| Variable | Required | Default | Description |
|----------|----------|---------|-------------|
| `VITE_API_URL` | No | `https://task3backend-vpcq.onrender.com/api` | Backend API URL |
| `VITE_WS_URL` | No | `https://task3backend-vpcq.onrender.com` | WebSocket server URL |

---

## 📱 Pages & Features

### Authentication Pages
- **Login** (`/login`) - User login with email & password
- **Register** (`/register`) - New user registration

### Main Pages
- **Dashboard** (`/`) - Overview of tasks, messages, and statistics
- **Tasks** (`/tasks`) - Kanban board and task management
- **Calendar** (`/calendar`) - Calendar view of task deadlines
- **Messages** (`/messages`) - Team messaging system
- **Team** (`/team`) - Team members and collaboration
- **Reports** (`/reports`) - Analytics and reports
- **Settings** (`/settings`) - User profile and preferences

---

## 🎨 UI Components

### Custom Components
- `Button` - Customizable button component
- `Input` - Text input with validation
- `Modal` - Dialog/modal component
- `Badge` - Status/tag badges
- `Avatar` - User avatar display
- `LoadingSpinner` - Loading animation

### Features
- Responsive design (mobile, tablet, desktop)
- Accessibility (WCAG 2.1 compliant)
- Dark mode support via Tailwind
- Smooth animations and transitions

---

## 🔗 API Integration

### Authentication Flow
1. User registers/logs in
2. Backend returns JWT token
3. Token stored in `auth-storage` (localStorage/Zustand)
4. Token automatically attached to API requests
5. Token sent via `Authorization: Bearer <token>` header

### Real-time Updates
1. Frontend connects to WebSocket via Socket.IO
2. Listens for task updates, messages, notifications
3. Automatic reconnection on disconnect
4. Real-time UI updates without page reload

---

## 📡 Connected APIs

### Base URL
- **Development:** `http://localhost:5000/api`
- **Production:** `https://task3backend-vpcq.onrender.com/api`

### Main Endpoints Used
- `POST /auth/login` - User login
- `POST /auth/register` - User registration
- `GET /tasks` - Fetch user tasks
- `POST /tasks` - Create new task
- `PUT /tasks/:id` - Update task
- `DELETE /tasks/:id` - Delete task
- `GET /messages` - Fetch messages
- `POST /messages` - Send message
- `GET /users` - Fetch team members

---

## 🧪 Testing

### Test Account
- **Email:** `admin@example.com`
- **Password:** `password123`

Or register a new account through the UI.

### Common Test Scenarios
1. Register new user
2. Login with email/password
3. Create, update, delete tasks
4. Change task status via Kanban
5. Send messages to team members
6. View calendar with tasks
7. Check reports and analytics

---

## 🐛 Troubleshooting

### API Connection Issues
- Verify backend is running
- Check `VITE_API_URL` is correct
- Open browser DevTools → Network tab
- Look for CORS errors in console

### WebSocket Connection Issues
- Check `VITE_WS_URL` is correct
- Verify backend WebSocket is enabled
- Check browser console for connection errors
- Try hard refresh (Ctrl+Shift+R)

### Build Errors
- Delete `node_modules/` and `package-lock.json`
- Run `npm install` again
- Clear Vite cache: `rm -rf dist node_modules/.vite`

### Performance Issues
- Check browser DevTools Performance tab
- Clear browser cache
- Disable browser extensions
- Use production build: `npm run build && npm run preview`

---

## 🚀 Deployment

### Vercel (Current)
- Automatically deploys on every push to `main` branch
- Environment variables set in Vercel dashboard
- Built-in CI/CD and SSL

### Alternative Hosting
- **Netlify:** Similar to Vercel
- **GitHub Pages:** For static SPA (no backend)
- **AWS Amplify:** AWS-managed deployment

---

## 📦 Dependencies

### Main
- `react` - UI library
- `react-dom` - React DOM renderer
- `axios` - HTTP client
- `zustand` - State management
- `socket.io-client` - WebSocket client
- `tailwindcss` - CSS framework
- `date-fns` - Date utilities
- `lucide-react` - Icons

### Dev
- `vite` - Build tool
- `typescript` - Type checking
- `tailwindcss` - CSS framework setup
- `postcss` - CSS processing
- `autoprefixer` - Browser prefix support

---

## 🔗 Related Projects

- **Backend API:** https://github.com/yaswanth65/task3Backend
- **Backend Live:** https://task3backend-vpcq.onrender.com

---

## 📄 License

This project is licensed under the MIT License.

---

## 👨‍💻 Author

**Yaswanth** - TaskFlow Frontend Developer

---

## 🤝 Support

For issues and questions, please create an issue in the repository or contact the development team.

---

## 🎯 Roadmap

- [ ] Dark mode toggle
- [ ] Task templates
- [ ] Advanced filtering & sorting
- [ ] Export tasks to CSV/PDF
- [ ] Mobile app (React Native)
- [ ] Offline support (IndexedDB)
- [ ] Custom notifications
- [ ] Team workspace separation
