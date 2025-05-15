# RoomLoop - Virtual Events and Meetups Platform (Client)

A modern React-based platform for virtual events, meetings, and social gatherings.

## Related Repositories

- **Backend Repository**: [roomloop-server](https://github.com/abhi21121211/roomloop-server) - The server-side codebase for RoomLoop platform

## Features


- **Live and Scheduled Rooms**: Create and join rooms that are live or scheduled for the future
- **Private and Public Rooms**: Host public events or create private rooms with invite-only access
- **Dashboard View**: Grid-based dashboard with pagination and filtering (live, upcoming, past)
- **Explore Page**: Discover public events and your private rooms with search functionality
- **Real-time Chat**: Live chat with message history for all room participants
- **Reactions**: Express yourself with emoji reactions during meetings
- **Room History**: View closed room details and chat history
- **User Management**: Registration, authentication, and profile management
- **Responsive Design**: Fully responsive UI that works on desktop and mobile devices

## Screenshots

<details>
<summary>View Application Screenshots</summary>

### Dashboard

![Dashboard Screenshot](/roomloop/client/screenshots/Screenshot%202025-05-04%20102141.png)

### Explore Rooms

![Explore Screenshot](/roomloop/client/screenshots/Screenshot%202025-05-04%20102201.png)

### Room View

![Room View Screenshot](/roomloop/client/screenshots/Screenshot%202025-05-04%20103258.png)

### Live Chat

![Live Chat Screenshot](/roomloop/client/screenshots/Screenshot%202025-05-04%20103101.png)

</details>

## Technology Stack

- **Frontend**: React, TypeScript, Material UI
- **State Management**: React Context API
- **Routing**: React Router
- **Real-time**: Socket.IO for live chat and reactions
- **Styling**: Styled components and Material UI theming
- **Authentication**: JWT-based authentication

## Getting Started

### Prerequisites

- Node.js (v14 or later)
- npm or yarn

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/abhi21121211/roomloop-client.git
   cd roomloop-client
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Create a `.env` file in the root directory with:

   ```
   REACT_APP_API_URL=http://localhost:5000/api
   ```

4. Start the development server:

   ```bash
   npm start
   ```

5. Open [http://localhost:3000](http://localhost:3000) to view the app in the browser.

## Deployment

### Deploying to Vercel

1. Create a Vercel account if you don't have one at [vercel.com](https://vercel.com)

2. Install Vercel CLI (optional):

   ```bash
   npm install -g vercel
   ```

3. Create a `vercel.json` file in the project root:

   ```json
   {
     "version": 2,
     "builds": [
       {
         "src": "package.json",
         "use": "@vercel/static-build"
       }
     ],
     "routes": [
       {
         "src": "/static/(.*)",
         "dest": "/static/$1"
       },
       {
         "src": "/favicon.ico",
         "dest": "/favicon.ico"
       },
       {
         "src": "/manifest.json",
         "dest": "/manifest.json"
       },
       {
         "src": "/(.*).(js|json|css|svg|png|jpg|jpeg|ico|ttf|woff|woff2)",
         "dest": "/$1.$2"
       },
       {
         "src": "/(.*)",
         "dest": "/index.html"
       }
     ],
     "env": {
       "REACT_APP_API_URL": "https://roomloop-server.onrender.com/api",
       "REACT_APP_SOCKET_URL": "https://roomloop-server.onrender.com"
     }
   }
   ```

4. Connect your repository to Vercel:

   - Log in to Vercel dashboard
   - Click "Add New" > "Project"
   - Import your Git repository
   - Set the framework preset to "Create React App"
   - Configure environment variables in the Vercel dashboard:
     - `REACT_APP_API_URL`: https://roomloop-server.onrender.com/api
     - `REACT_APP_SOCKET_URL`: https://roomloop-server.onrender.com

5. Deploy the application:

   - If using CLI: Run `vercel` in the project directory
   - If using dashboard: The deployment will start automatically

6. Your application will be deployed to a URL like `roomloop.vercel.app`

### Troubleshooting Deployment Issues

If you encounter dependency resolution errors during deployment:

1. **Version compatibility issues**: Make sure React and TypeScript type definitions are compatible with Material UI:

   - React 18.x is recommended with @types/react ^18.2.x
   - React 19.x may have compatibility issues with some MUI components

2. **Builder errors**: Ensure you're using the correct Vercel builder:
   - For React apps, use `@vercel/static-build` instead of `@vercel/node`
3. **Build script**: Make sure your package.json includes a `vercel-build` script:

   ```
   "scripts": {
     "vercel-build": "npm run build"
   }
   ```

4. **Environment variables**: Double-check that all required environment variables are set in Vercel dashboard

## Available Scripts

- `npm start` - Runs the app in development mode
- `npm test` - Launches the test runner
- `npm run build` - Builds the app for production
- `npm run eject` - Ejects the create-react-app configuration

## Project Structure

```
src/
├── components/    # Reusable UI components
├── contexts/      # React contexts for state management
├── pages/         # Main page components
├── services/      # API and external service integrations
├── types/         # TypeScript type definitions
├── utils/         # Utility functions
└── App.tsx        # Main application component
```

## Key Features in Detail

### Dashboard

- Grid layout of rooms with tabs for filtering (live, upcoming, past)
- Pagination for large lists of rooms
- Quick access to rooms you've created or been invited to

### Explore

- Browse public rooms or private rooms you have access to
- Search by title, description, or tags
- Filter between public and private rooms

### Room View

- Live chat with real-time updates
- User presence indicators
- Participant list with roles (host, guest)
- Room details and information
- View chat history for closed rooms

### Room End Alert

- Option to view room history or return to dashboard when a room ends
- Persistent preferences for viewing closed rooms

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
