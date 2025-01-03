# MERN Blog Application with User Authentication and Post Management

This project is a full-stack blog application built using the MERN (MongoDB, Express, React, Node.js) stack with user authentication and post management features.

The application allows users to create accounts, sign in, create and manage blog posts, and interact with other users' content through comments and likes. It features a responsive design, rich text editing, and image upload capabilities.

## Repository Structure

The repository is organized into two main directories: `api` for the backend and `client` for the frontend.

### API (Backend)

- `controllers/`: Contains the logic for handling requests and responses
- `models/`: Defines the data models for MongoDB
- `routes/`: Defines the API endpoints
- `utils/`: Utility functions and middleware
- `index.js`: Entry point for the Express server

### Client (Frontend)

- `src/`: Contains the React application source code
  - `components/`: Reusable React components
  - `pages/`: Individual page components
  - `redux/`: Redux store and slices for state management
- `public/`: Static assets
- `vite.config.js`: Vite configuration for the development server and build process

## Usage Instructions

### Installation

1. Clone the repository
2. Install dependencies for both the backend and frontend:

```bash
npm install
cd client
npm install
```

3. Set up environment variables:
   - Create a `.env` file in the root directory
   - Add the following variables:
     ```
     MONGO=your_mongodb_connection_string
     JWT_SECRET=your_jwt_secret
     ```
   - Create a `.env` file in the `client` directory
   - Add the following variable:
     ```
     VITE_FIREBASE_API_KEY=your_firebase_api_key
     ```

### Running the Application

1. Start the backend server:

```bash
npm run dev
```

2. Start the frontend development server:

```bash
cd client
npm run dev
```

3. Access the application at `http://localhost:5173`

### Creating a Post

1. Sign in to your account
2. Navigate to the "Create Post" page
3. Fill in the title, select a category, and write your content using the rich text editor
4. Optionally upload an image for your post
5. Click "Publish" to create your post

### Managing Posts

- View all posts on the home page
- Click on a post to view its details
- Edit or delete your own posts from the dashboard

### Commenting and Liking

- Leave comments on posts
- Like or unlike comments
- Edit or delete your own comments

## Data Flow

1. User interacts with the React frontend
2. Frontend makes API calls to the Express backend
3. Backend processes requests, interacts with MongoDB, and returns responses
4. Frontend updates state using Redux and re-renders components

```
[User] <-> [React Frontend] <-> [Express Backend] <-> [MongoDB]
```

## Infrastructure

The application uses Firebase for authentication and file storage:

- Firebase Authentication: Handles user sign-up and sign-in
- Firebase Storage: Stores uploaded images for blog posts

```javascript
// Firebase configuration
const firebaseConfig = {
  apiKey: import.meta.env.VITE_FIREBASE_API_KEY,
  authDomain: "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX",
  projectId: "",
  storageBucket: "XXXXXXXXXXXXXXXXXXXXXXXXXXX",
  messagingSenderId: "699397991367",
  appId: "1:699397991367:web:88ff565ef72a182d6b87e2",
};
```

The backend is configured to serve the frontend build in production, enabling deployment as a single application.