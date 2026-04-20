# Geo-Bite 🍕📍

A location-based cafe discovery and review application backend. Users can explore cafes in their area, read reviews, and share their own dining experiences.

## Features

- 🔐 **User Authentication** - JWT-based authentication with bcryptjs password hashing
- 🏪 **Cafe Listings** - Browse and filter cafes by location
- ⭐ **Reviews & Ratings** - Users can leave and read cafe reviews
- 🔗 **RESTful API** - Clean and organized API endpoints
- 📦 **MongoDB Integration** - Persistent data storage
- 🛡️ **CORS Enabled** - Safe cross-origin requests

## Tech Stack

- **Runtime:** Node.js
- **Framework:** Express.js
- **Database:** MongoDB
- **Authentication:** JWT (JSON Web Tokens)
- **Password Hashing:** bcryptjs
- **CORS:** Cross-origin resource sharing

## Prerequisites

Before you begin, ensure you have the following installed:
- [Node.js](https://nodejs.org/) (v14 or higher)
- [MongoDB](https://www.mongodb.com/) (local or Atlas cloud)
- npm or yarn

## Installation

1. **Clone the repository**
```bash
git clone https://github.com/UtsavTiwari09/Geo_Bite.git
cd Geo-Bite
```

2. **Install dependencies**
```bash
npm install
```

3. **Create a `.env` file** in the root directory and add your environment variables:
```env
PORT=3000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
JWT_EXPIRE=30d
```

4. **Start the server**
```bash
# Development mode (with auto-reload)
npm run dev

# Production mode
npm start
```

The server will run on `http://localhost:3000`

## API Endpoints

### Authentication Routes (`/api/auth`)
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login user
- `POST /api/auth/logout` - Logout user

### Cafe Routes (`/api/cafes`)
- `GET /api/cafes` - Get all cafes
- `GET /api/cafes/:id` - Get a specific cafe
- `POST /api/cafes` - Create a new cafe (admin only)
- `PUT /api/cafes/:id` - Update a cafe (admin only)
- `DELETE /api/cafes/:id` - Delete a cafe (admin only)

### Review Routes (`/api/cafes/:cafeId/reviews`)
- `GET /api/cafes/:cafeId/reviews` - Get all reviews for a cafe
- `POST /api/cafes/:cafeId/reviews` - Create a new review
- `PUT /api/cafes/:cafeId/reviews/:reviewId` - Update a review
- `DELETE /api/cafes/:cafeId/reviews/:reviewId` - Delete a review

## Project Structure

```
Geo-Bite/
├── config/
│   └── db.js                 # MongoDB connection configuration
├── controllers/
│   ├── auth.controllers.js   # Authentication logic
│   ├── Cafe.controllers.js   # Cafe management logic
│   └── review.controllers.js # Review management logic
├── middlewares/
│   └── auth.middlewares.js   # JWT verification middleware
├── models/
│   ├── User.models.js        # User schema
│   ├── Cafe.models.js        # Cafe schema
│   └── Review.models.js      # Review schema
├── routes/
│   ├── auth.routes.js        # Authentication routes
│   ├── cafe.routes.js        # Cafe routes
│   └── review.routes.js      # Review routes
├── .env                      # Environment variables (not in repo)
├── .gitignore                # Git ignore file
├── package.json              # Dependencies
├── seeder.js                 # Database seeding script (optional)
└── server.js                 # Main server file
```

## Environment Variables

| Variable | Description | Example |
|----------|-------------|---------|
| `PORT` | Server port | `3000` |
| `MONGO_URI` | MongoDB connection string | `mongodb+srv://user:pass@cluster.mongodb.net/geobite` |
| `JWT_SECRET` | Secret key for JWT signing | `your_secret_key_here` |
| `JWT_EXPIRE` | JWT expiration time | `30d` |

## Development

To run the server in development mode with auto-reload:
```bash
npm run dev
```

This uses `nodemon` to automatically restart the server when files change.

## Database Seeding

To seed the database with initial data (if available):
```bash
node seeder.js
```

## Contributing

1. Fork the repository
2. Create a new branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the ISC License - see the [LICENSE](LICENSE) file for details.

## Contact

- **Author:** Utsav Tiwari
- **GitHub:** [@UtsavTiwari09](https://github.com/UtsavTiwari09)
- **Project Link:** [Geo_Bite](https://github.com/UtsavTiwari09/Geo_Bite)

## Roadmap

- [ ] Add location-based filtering
- [ ] Implement image uploads for cafes and reviews
- [ ] Add user profiles and preferences
- [ ] Integrate Google Maps API
- [ ] Add pagination to cafe listings
- [ ] Implement admin dashboard
- [ ] Add email verification for sign-up

## Support

For support, email your_email@example.com or open an issue on GitHub.
