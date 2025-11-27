# 🎬 CineFlix - Online Movie Ticketing System

A comprehensive web-based movie ticketing platform that enables users to browse movies, check showtimes, and book tickets online with a seamless user experience.

**Developer:** Aparup Chowdhury  
**Technologies:** PHP, MySQL, JavaScript, HTML5, CSS3  
**Category:** Full-Stack Web Application  
**Status:** 🟢 Active Development

---

## 📋 Table of Contents
- [Project Overview](#-project-overview)
- [Features](#-features)
- [Technology Stack](#-technology-stack)
- [System Architecture](#-system-architecture)
- [Installation](#-installation)
- [Database Setup](#-database-setup)
- [Usage Guide](#-usage-guide)
- [Screenshots](#-screenshots)
- [API Endpoints](#-api-endpoints)
- [Security Features](#-security-features)
- [Future Enhancements](#-future-enhancements)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 Project Overview

CineFlix is a modern online movie ticketing system designed to streamline the movie booking experience. The platform provides a complete solution for cinema management, from movie listings to seat selection and payment processing, offering both customers and administrators an intuitive interface for all ticketing operations.

### Key Highlights

- **Real-time Seat Selection**: Interactive seat map with live availability
- **Secure Payment Integration**: Multiple payment gateway support
- **Responsive Design**: Seamless experience across all devices
- **Admin Dashboard**: Comprehensive management tools for theaters
- **User Authentication**: Secure login and registration system

---

## ✨ Features

### Customer Features
- 🎭 **Browse Movies**: View current and upcoming movies with detailed information
- 🪑 **Seat Selection**: Interactive seat map with real-time availability
- 📅 **Showtime Management**: View and select from available showtimes
- 💳 **Online Payment**: Secure payment processing with multiple options
- 📧 **E-Tickets**: Digital ticket generation and email confirmation
- 👤 **User Profile**: Manage bookings and view history
- ⭐ **Ratings & Reviews**: Rate and review movies
- 🔍 **Search & Filter**: Find movies by genre, language, or rating

### Admin Features
- 🎬 **Movie Management**: Add, edit, and remove movie listings
- 🏛️ **Theater Management**: Configure halls and seating layouts
- 📊 **Booking Analytics**: View booking trends and revenue reports
- 👥 **User Management**: Manage customer accounts and permissions
- 💰 **Price Configuration**: Set dynamic pricing for different shows
- 📈 **Dashboard**: Real-time statistics and performance metrics
- 🎟️ **Ticket Validation**: Verify and manage ticket bookings
- 📢 **Promotions**: Create and manage discount offers

---

## 🛠️ Technology Stack

### Frontend
- **HTML5**: Semantic markup structure
- **CSS3**: Modern styling with animations
- **JavaScript**: Dynamic interactions and AJAX
- **Bootstrap**: Responsive framework
- **jQuery**: DOM manipulation and effects

### Backend
- **PHP 7.4+**: Server-side logic and processing
- **MySQL**: Database management system
- **Apache/Nginx**: Web server
- **PHPMailer**: Email notifications

### Additional Tools
- **AJAX**: Asynchronous data loading
- **JSON**: Data exchange format
- **Chart.js**: Analytics visualization
- **Font Awesome**: Icon library
- **SweetAlert2**: Beautiful alerts

---

## 🏗️ System Architecture

```
CineFlix/
├── 📁 assets/
│   ├── css/
│   │   ├── style.css
│   │   ├── admin.css
│   │   └── responsive.css
│   ├── js/
│   │   ├── main.js
│   │   ├── booking.js
│   │   └── admin.js
│   └── images/
│       ├── movies/
│       └── logos/
├── 📁 includes/
│   ├── config.php
│   ├── db_connect.php
│   ├── functions.php
│   └── header.php
├── 📁 admin/
│   ├── dashboard.php
│   ├── movies.php
│   ├── bookings.php
│   └── users.php
├── 📁 user/
│   ├── profile.php
│   ├── bookings.php
│   └── tickets.php
├── 📁 database/
│   └── cineflix.sql
├── index.php
├── login.php
├── register.php
├── movies.php
├── booking.php
├── payment.php
└── README.md
```

---

## 🚀 Installation

### Prerequisites
- PHP >= 7.4
- MySQL >= 5.7
- Apache/Nginx Web Server
- Composer (for dependencies)

### Step 1: Clone Repository
```bash
git clone https://github.com/aparup-chy/CineFlix.git
cd CineFlix
```

### Step 2: Configure Database
1. Create a MySQL database
```sql
CREATE DATABASE cineflix;
```

2. Import the database schema
```bash
mysql -u username -p cineflix < database/cineflix.sql
```

### Step 3: Configure Connection
Edit `includes/config.php`:
```php
<?php
define('DB_HOST', 'localhost');
define('DB_USER', 'your_username');
define('DB_PASS', 'your_password');
define('DB_NAME', 'cineflix');
?>
```

### Step 4: Set Permissions
```bash
chmod 755 -R CineFlix/
chmod 777 assets/images/movies/
```

### Step 5: Start Server
```bash
# For built-in PHP server
php -S localhost:8000

# Or configure with Apache/Nginx
```

---

## 💾 Database Setup

### Database Schema

#### Tables Structure

**users**
- `id` (INT, Primary Key, Auto Increment)
- `username` (VARCHAR 50, Unique)
- `email` (VARCHAR 100, Unique)
- `password` (VARCHAR 255, Hashed)
- `phone` (VARCHAR 15)
- `created_at` (TIMESTAMP)
- `role` (ENUM: 'customer', 'admin')

**movies**
- `id` (INT, Primary Key)
- `title` (VARCHAR 200)
- `description` (TEXT)
- `genre` (VARCHAR 100)
- `duration` (INT)
- `language` (VARCHAR 50)
- `release_date` (DATE)
- `poster` (VARCHAR 255)
- `rating` (DECIMAL)
- `status` (ENUM: 'showing', 'upcoming')

**bookings**
- `id` (INT, Primary Key)
- `user_id` (INT, Foreign Key)
- `show_id` (INT, Foreign Key)
- `seats` (VARCHAR 255)
- `total_amount` (DECIMAL)
- `payment_status` (ENUM: 'pending', 'completed', 'failed')
- `booking_date` (TIMESTAMP)

**shows**
- `id` (INT, Primary Key)
- `movie_id` (INT, Foreign Key)
- `theater_id` (INT, Foreign Key)
- `show_time` (DATETIME)
- `price` (DECIMAL)
- `available_seats` (INT)

**theaters**
- `id` (INT, Primary Key)
- `name` (VARCHAR 100)
- `total_seats` (INT)
- `seat_layout` (JSON)

---

## 📖 Usage Guide

### For Customers

1. **Registration/Login**
   - Create an account or login to existing account
   - Verify email (if enabled)

2. **Browse Movies**
   - View all available movies
   - Filter by genre, language, or rating
   - Check movie details and reviews

3. **Book Tickets**
   - Select movie and preferred showtime
   - Choose seats from interactive map
   - Review booking details

4. **Payment**
   - Enter payment information
   - Confirm booking
   - Receive e-ticket via email

5. **Manage Bookings**
   - View booking history
   - Download tickets
   - Cancel bookings (if policy allows)

### For Administrators

1. **Access Admin Panel**
   - Login with admin credentials
   - Navigate to `/admin/dashboard.php`

2. **Manage Movies**
   - Add new movie listings
   - Update movie information
   - Set movie status (showing/upcoming)

3. **Configure Shows**
   - Schedule showtimes
   - Set pricing
   - Manage seat availability

4. **Monitor Bookings**
   - View real-time booking data
   - Generate reports
   - Handle refunds/cancellations

---

## 📸 Screenshots

### Customer Interface
- **Homepage**: Movie carousel and featured listings
- **Movie Details**: Comprehensive movie information
- **Seat Selection**: Interactive seat map
- **Payment Gateway**: Secure checkout process
- **E-Ticket**: Digital ticket with QR code

### Admin Dashboard
- **Analytics Dashboard**: Revenue and booking statistics
- **Movie Management**: CRUD operations for movies
- **Booking Overview**: Real-time booking monitoring
- **User Management**: Customer account administration

---

## 🔌 API Endpoints

### Public APIs
```
GET  /api/movies          - List all movies
GET  /api/movies/{id}     - Get movie details
GET  /api/shows/{movie}   - Get showtimes for a movie
GET  /api/seats/{show}    - Get seat availability
```

### Protected APIs (Authentication Required)
```
POST /api/bookings        - Create new booking
GET  /api/user/bookings   - Get user bookings
POST /api/user/profile    - Update user profile
```

### Admin APIs
```
POST   /api/admin/movies     - Add new movie
PUT    /api/admin/movies/{id} - Update movie
DELETE /api/admin/movies/{id} - Delete movie
GET    /api/admin/analytics   - Get analytics data
```

---

## 🔐 Security Features

- **Password Encryption**: BCrypt hashing for passwords
- **SQL Injection Prevention**: Prepared statements and parameterized queries
- **XSS Protection**: Input sanitization and output encoding
- **CSRF Protection**: Token-based form validation
- **Session Security**: Secure session handling
- **HTTPS Enforcement**: SSL/TLS encryption
- **Rate Limiting**: API request throttling
- **Input Validation**: Server-side validation for all inputs

---

## 🚧 Future Enhancements

### Phase 1 (Next Release)
- [ ] Mobile application (iOS/Android)
- [ ] Multiple language support
- [ ] Social media integration
- [ ] Advanced search filters
- [ ] Loyalty program implementation

### Phase 2 (Planned)
- [ ] AI-based movie recommendations
- [ ] Virtual reality seat preview
- [ ] Group booking features
- [ ] Live chat support
- [ ] Integration with more payment gateways

### Phase 3 (Future)
- [ ] Blockchain-based ticketing
- [ ] Dynamic pricing algorithm
- [ ] Augmented reality features
- [ ] Voice-based booking
- [ ] API for third-party integration

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create your feature branch
```bash
git checkout -b feature/AmazingFeature
```
3. Commit your changes
```bash
git commit -m 'Add some AmazingFeature'
```
4. Push to the branch
```bash
git push origin feature/AmazingFeature
```
5. Open a Pull Request

### Coding Standards
- Follow PSR-12 for PHP code
- Use meaningful variable names
- Comment complex logic
- Write unit tests for new features

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**Aparup Chowdhury**
- GitHub: [@aparup-chy](https://github.com/aparup-chy)
- Email: [contact@email.com]
- Portfolio: [Your Portfolio]

---

## 🙏 Acknowledgments

- Bootstrap for the responsive framework
- jQuery community for excellent documentation
- Font Awesome for icons
- All contributors and testers

---

## 📞 Support

For support, please:
- Open an issue on GitHub
- Email at support@cineflix.com
- Check the [Wiki](https://github.com/aparup-chy/CineFlix/wiki) for FAQs

---

## 🌟 Star History

If you find this project useful, please consider giving it a star ⭐

---

*CineFlix - Making movie booking simple, secure, and enjoyable!*