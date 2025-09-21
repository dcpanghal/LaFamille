# LaFamille 👨‍👩‍👧‍👦

A full-stack social media application built with React and Node.js that allows users to connect, share posts, and build their social network.

![LaFamille](https://img.shields.io/badge/LaFamille-Social%20Media%20App-blue)
![React](https://img.shields.io/badge/React-17.0.2-blue)
![Node.js](https://img.shields.io/badge/Node.js-Express-green)
![MongoDB](https://img.shields.io/badge/Database-MongoDB-green)

## 🌟 Features

### 🔐 Authentication & Security
- **User Registration & Login** with secure JWT authentication
- **Password Reset** functionality via email
- **Profile Picture** upload and management
- **Secure password hashing** using bcrypt

### 📱 Social Features
- **Create Posts** with images and descriptions
- **Like & Comment** on posts
- **Follow/Unfollow** other users
- **Personal Profile** management
- **View User Profiles** and their posts
- **Following Feed** to see posts from followed users

### 📧 Email Integration
- **Welcome emails** on account creation
- **Password reset emails** with secure tokens
- **SendGrid integration** for reliable email delivery

### 🎨 User Interface
- **Responsive design** using Materialize CSS
- **Mobile-friendly** navigation with sidebar
- **Real-time updates** and interactive UI
- **Clean and modern** design

## 🛠️ Tech Stack

### Frontend
- **React** 17.0.2 - UI library
- **React Router DOM** - Client-side routing
- **Materialize CSS** - UI framework
- **Context API** - State management

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM for MongoDB

### Authentication & Security
- **JWT (JSON Web Tokens)** - Authentication
- **bcryptjs** - Password hashing
- **CORS** - Cross-origin resource sharing

### Email Services
- **SendGrid** - Email delivery service
- **Nodemailer** - Email sending library

## 📁 Project Structure

```
LaFamille/
├── server/                 # Backend application
│   ├── config/            # Configuration files
│   │   ├── dev.js         # Development config
│   │   ├── prod.js        # Production config
│   │   └── keys.js        # Environment-based config
│   ├── middleware/        # Custom middleware
│   ├── models/           # Database models
│   │   ├── user.js       # User schema
│   │   └── post.js       # Post schema
│   ├── routes/           # API routes
│   │   ├── auth.js       # Authentication routes
│   │   ├── post.js       # Post-related routes
│   │   └── user.js       # User-related routes
│   ├── client/           # Frontend React application
│   │   ├── src/
│   │   │   ├── components/
│   │   │   │   ├── screens/  # Page components
│   │   │   │   └── Navbar.js # Navigation component
│   │   │   ├── reducers/     # State management
│   │   │   └── App.js        # Main app component
│   │   └── public/
│   ├── package.json      # Backend dependencies
│   └── app.js           # Server entry point
└── README.md
```

## 🚀 Getting Started

### Prerequisites
- **Node.js** (v14 or higher)
- **MongoDB** (local installation or MongoDB Atlas)
- **SendGrid Account** (for email functionality)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/dcpanghal/LaFamille.git
   cd LaFamille
   ```

2. **Install server dependencies**
   ```bash
   cd server
   npm install
   ```

3. **Install client dependencies**
   ```bash
   cd client
   npm install
   cd ..
   ```

4. **Environment Configuration**

   Create your environment variables based on your setup:

   **For Development** (server/config/dev.js):
   ```javascript
   module.exports = {
       MONGOURI: "mongodb://localhost:27017/lafamille",
       JWT_SECRET: "your_jwt_secret_key_here",
       SENDGRID_API: "your_sendgrid_api_key_here",
       EMAIL: "your_email@example.com"
   }
   ```

   **For Production** (Environment Variables):
   ```bash
   MONGOURI=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret_key
   SENDGRID_API=your_sendgrid_api_key
   EMAIL=your_email@example.com
   NODE_ENV=production
   ```

5. **Start the application**

   **Development Mode:**
   ```bash
   # Start backend server (from server directory)
   npm start

   # Start frontend client (from server/client directory)
   cd client
   npm start
   ```

   **Production Mode:**
   ```bash
   # From server directory
   npm start
   ```

### 🔧 Configuration Details

#### MongoDB Setup
- **Local MongoDB**: Install MongoDB locally and ensure it's running on port 27017
- **MongoDB Atlas**: Create a cluster and get your connection string

#### SendGrid Setup
1. Create a SendGrid account
2. Generate an API key
3. Add your API key to the configuration

#### JWT Secret
Generate a secure random string for JWT token signing:
```bash
node -e "console.log(require('crypto').randomBytes(64).toString('hex'))"
```

## 📱 Usage

### User Registration
1. Navigate to `/signup`
2. Fill in your details (name, email, password, profile picture)
3. Check your email for welcome message
4. Login with your credentials

### Creating Posts
1. Login to your account
2. Navigate to "Create Post"
3. Add title, description, and image
4. Share with your network

### Social Interactions
- **Like posts** by clicking the heart icon
- **Comment** on posts to engage with users
- **Follow users** to see their posts in your feed
- **View profiles** to see user information and posts

## 🌐 API Endpoints

### Authentication Routes
- `POST /signup` - User registration
- `POST /signin` - User login
- `POST /reset-password` - Password reset request
- `POST /new-password` - Set new password

### Post Routes
- `GET /allpost` - Get all posts
- `GET /mypost` - Get user's posts
- `POST /createpost` - Create new post
- `PUT /like` - Like/unlike post
- `PUT /comment` - Add comment to post

### User Routes
- `GET /user/:id` - Get user profile
- `PUT /follow` - Follow/unfollow user
- `PUT /updatepic` - Update profile picture

## 🔒 Security Features

- **Password Hashing**: All passwords are hashed using bcrypt
- **JWT Authentication**: Secure token-based authentication
- **Input Validation**: Server-side validation for all inputs
- **CORS Protection**: Configured for secure cross-origin requests
- **Environment Variables**: Sensitive data stored in environment variables

## 🎨 UI Components

### Screens
- **Home** - Main feed with all posts
- **Profile** - User profile management
- **Create Post** - Post creation interface
- **Sign In/Sign Up** - Authentication forms
- **User Profile** - View other users' profiles
- **Following Feed** - Posts from followed users
- **Password Reset** - Password recovery interface

### Features
- **Responsive Navigation** with mobile sidebar
- **Material Design** components
- **Real-time UI updates**
- **Image upload** and display

## 🚀 Deployment

### Heroku Deployment

1. **Prepare for deployment**
   ```bash
   # Ensure you have Heroku CLI installed
   heroku login
   ```

2. **Create Heroku app**
   ```bash
   heroku create your-app-name
   ```

3. **Set environment variables**
   ```bash
   heroku config:set MONGOURI=your_mongodb_atlas_uri
   heroku config:set JWT_SECRET=your_jwt_secret
   heroku config:set SENDGRID_API=your_sendgrid_api_key
   heroku config:set EMAIL=your_email@example.com
   heroku config:set NODE_ENV=production
   ```

4. **Deploy**
   ```bash
   git push heroku main
   ```

### Other Deployment Options
- **Vercel** - For frontend deployment
- **Railway** - Full-stack deployment
- **DigitalOcean** - VPS deployment
- **AWS** - Cloud deployment

## 🧪 Testing

### Running Tests
```bash
# Frontend tests
cd server/client
npm test

# Backend tests (if implemented)
cd server
npm test
```

### Test Coverage
- Component rendering tests
- API endpoint tests
- Authentication flow tests
- Database operation tests

## 🤝 Contributing

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Commit your changes**
   ```bash
   git commit -m 'Add some amazing feature'
   ```
4. **Push to the branch**
   ```bash
   git push origin feature/amazing-feature
   ```
5. **Open a Pull Request**

### Development Guidelines
- Follow React best practices
- Use meaningful commit messages
- Add comments for complex logic
- Test your changes thoroughly
- Update documentation as needed

## 📝 License

This project is licensed under the ISC License - see the [LICENSE](LICENSE) file for details.

## 👥 Authors

- **Developer** - [dcpanghal](https://github.com/dcpanghal)

## 🙏 Acknowledgments

- **React Team** for the amazing framework
- **MongoDB** for the database solution
- **SendGrid** for email services
- **Materialize CSS** for the UI components
- **Heroku** for hosting platform

## 📞 Support

If you have any questions or need help with setup, please:

1. Check the [Issues](https://github.com/dcpanghal/LaFamille/issues) page
2. Create a new issue if your problem isn't already listed
3. Provide detailed information about your setup and the issue

## 🔮 Future Enhancements

- [ ] **Real-time messaging** between users
- [ ] **Story feature** with temporary posts
- [ ] **Video upload** support
- [ ] **Advanced search** functionality
- [ ] **Push notifications**
- [ ] **Dark mode** theme
- [ ] **Mobile app** development
- [ ] **Advanced privacy** settings
- [ ] **Content moderation** tools
- [ ] **Analytics dashboard**

---

**Made with ❤️ by Mandeep Kumar!

*Connect, Share, and Build Your Digital Family!*
