# Expense Tracker Application

A modern full-stack expense management application built with Angular 22 frontend and Spring Boot 4.1 backend API for tracking and managing personal and organizational expenses.

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Setup & Installation](#setup--installation)
- [Running the Application](#running-the-application)
- [API Endpoints](#api-endpoints)
- [Features](#features)
- [Development](#development)
- [Testing](#testing)
- [Configuration](#configuration)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)

## 🎯 Project Overview

The Expense Tracker Application is a comprehensive solution for managing and tracking expenses. It provides users with a user-friendly interface to record expenses, categorize them, track spending patterns, and generate reports for better financial management.

**Key Use Cases:**
- Personal expense tracking
- Budget management
- Spending analysis and reports
- Multi-category expense organization
- Expense history and tracking

## 🛠️ Tech Stack

### Frontend
- **Angular 22.1** - Modern web framework
- **TypeScript 6.0** - Type-safe JavaScript
- **RxJS 7.8** - Reactive programming
- **Angular Router** - Client-side routing
- **Angular Forms** - Form handling and validation

### Backend
- **Spring Boot 4.1.2** - Java web framework
- **Java 17** - LTS Java version
- **Spring MVC** - Web MVC framework
- **REST API** - RESTful API design

### Testing & Build
- **Vitest 4.0** - Frontend unit testing
- **JUnit** - Backend unit testing
- **Maven** - Java build tool
- **Angular CLI 22.1** - Frontend build tooling

## 📁 Project Structure

```
Expense_Tracker_App/
├── expense-tracker/                        # Spring Boot backend
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/evans/expense_tracker/
│   │   │   │   ├── controller/            # REST API endpoints
│   │   │   │   ├── service/               # Business logic
│   │   │   │   ├── model/                 # Entity models
│   │   │   │   └── ExpenseTrackerApplication.java
│   │   │   └── resources/
│   │   │       └── application.properties # Configuration
│   │   └── test/                          # Unit tests
│   ├── pom.xml                           # Maven configuration
│   ├── mvnw                              # Maven wrapper
│   └── HELP.md                           # Additional help
│
├── Expense_tracker/                       # Angular frontend
│   ├── src/
│   │   ├── app/
│   │   │   ├── app.ts                    # Main component
│   │   │   ├── app.routes.ts             # Route configuration
│   │   │   ├── app.config.ts             # App configuration
│   │   │   ├── app.html                  # Main template
│   │   │   ├── app.css                   # Styles
│   │   │   └── app.spec.ts               # Unit tests
│   │   ├── index.html                    # HTML entry point
│   │   ├── main.ts                       # Bootstrap file
│   │   └── styles.css                    # Global styles
│   ├── angular.json                      # Angular CLI config
│   ├── package.json                      # NPM dependencies
│   ├── tsconfig.json                     # TypeScript config
│   └── README.md                         # Frontend documentation
│
└── README.md                             # This file
```

## 📦 Prerequisites

Before you begin, ensure you have the following installed:

- **Java 17+** - [Download JDK](https://www.oracle.com/java/technologies/downloads/)
- **Node.js 18+** - [Download Node.js](https://nodejs.org/)
- **npm 12+** - Comes with Node.js
- **Git** - For version control

## ⚙️ Setup & Installation

### 1. Clone the Repository

```bash
git clone https://github.com/1337-KB/Expense_Tracker_App.git
cd Expense_Tracker_App
```

### 2. Backend Setup (Spring Boot API)

```bash
cd expense-tracker

# Install dependencies (Maven)
mvnw clean install

# Or if Maven is installed globally
mvn clean install
```

### 3. Frontend Setup (Angular)

```bash
cd Expense_tracker

# Install dependencies
npm install

# Or using npm ci for exact versions
npm ci
```

## 🚀 Running the Application

### Start Backend API

```bash
cd expense-tracker

# Using Maven wrapper
mvnw spring-boot:run

# Or using Maven directly (if installed)
mvn spring-boot:run
```

The API will start on **http://localhost:8080**

### Start Frontend Application

```bash
cd Expense_tracker

# Development server with hot reload
npm start

# Or using Angular CLI directly
ng serve

# For development with detailed output
ng serve --open
```

The frontend will start on **http://localhost:4200** and automatically open in your browser.

## 📡 API Endpoints

### Base URL
```
http://localhost:8080/api/expenses
```

### Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/expenses` | Get all expenses |
| GET | `/api/expenses/{id}` | Get expense by ID |
| POST | `/api/expenses` | Create new expense |
| PUT | `/api/expenses/{id}` | Update expense |
| DELETE | `/api/expenses/{id}` | Delete expense |
| GET | `/api/expenses/category/{category}` | Get expenses by category |
| GET | `/api/expenses/stats` | Get expense statistics |

### Example Requests

**Get All Expenses:**
```bash
curl http://localhost:8080/api/expenses
```

**Get Single Expense:**
```bash
curl http://localhost:8080/api/expenses/1
```

**Create Expense:**
```bash
curl -X POST http://localhost:8080/api/expenses \
  -H "Content-Type: application/json" \
  -d '{
    "description": "Grocery Shopping",
    "amount": 45.50,
    "category": "Food",
    "date": "2024-11-18"
  }'
```

**Get Expenses by Category:**
```bash
curl http://localhost:8080/api/expenses/category/Food
```

**Get Expense Statistics:**
```bash
curl http://localhost:8080/api/expenses/stats
```

**Update Expense:**
```bash
curl -X PUT http://localhost:8080/api/expenses/1 \
  -H "Content-Type: application/json" \
  -d '{
    "description": "Grocery Shopping - Updated",
    "amount": 50.00,
    "category": "Food",
    "date": "2024-11-18"
  }'
```

**Delete Expense:**
```bash
curl -X DELETE http://localhost:8080/api/expenses/1
```

## ✨ Features

### Expense Management
- ✅ Record new expenses with description, amount, and category
- ✅ View all recorded expenses in a list
- ✅ View detailed expense information
- ✅ Update existing expense details
- ✅ Delete expense records
- ✅ Filter expenses by category
- ✅ View expense statistics and summaries

### Financial Analysis
- ✅ Categorize expenses (Food, Transport, Entertainment, etc.)
- ✅ Track spending patterns
- ✅ Generate expense reports
- ✅ View spending statistics by category
- ✅ Monthly and yearly expense summaries

### Frontend Features
- Responsive design for desktop and mobile
- Real-time form validation
- Error handling and user feedback
- Smooth navigation between views
- Component-based architecture
- Currency support

### Backend Features
- RESTful API design
- CORS support for frontend integration
- Logging and monitoring
- Data persistence
- Efficient database queries
- Statistical aggregations

## 🔧 Development

### Frontend Development

#### Generate Components
```bash
cd Expense_tracker
ng generate component component-name
```

#### File Structure
- **Components** - Reusable UI elements for expense tracking
- **Services** - API communication and business logic
- **Models** - TypeScript interfaces for expenses
- **Routes** - Application navigation

#### Hot Reload
Changes to source files automatically reload the browser during development.

### Backend Development

#### Project Structure
- **Controllers** - HTTP request handlers for expense endpoints
- **Services** - Business logic for expense management
- **Models** - Expense entity definitions
- **Repositories** - Database access layer

#### Logging
Logs are configured in Spring Boot. Check console for debug information during development.

## 🧪 Testing

### Frontend Unit Tests

```bash
cd Expense_tracker

# Run tests
npm test

# Or with Angular CLI
ng test

# Run tests with coverage
ng test --code-coverage
```

### Backend Unit Tests

```bash
cd expense-tracker

# Run tests
mvnw test

# Or with Maven
mvn test

# Run specific test
mvnw test -Dtest=ExpenseTrackerControllerTest
```

### End-to-End Testing (Frontend)

```bash
cd Expense_tracker
ng e2e
```

## 🗄️ Database

### Expense Entity

The application uses an `Expense` entity with the following fields:

- **id** - Unique identifier (UUID/Auto-increment)
- **description** - Expense description
- **amount** - Expense amount (decimal)
- **category** - Expense category (Food, Transport, Entertainment, etc.)
- **date** - Expense date
- **createdAt** - Record creation timestamp
- **updatedAt** - Last update timestamp
- **tags** - Optional tags for organization

### Common Categories

- **Food & Dining** - Groceries, restaurants, cafes
- **Transportation** - Gas, public transit, vehicle maintenance
- **Entertainment** - Movies, games, hobbies
- **Utilities** - Electricity, water, internet
- **Healthcare** - Medical expenses, prescriptions
- **Shopping** - Clothing, personal items
- **Education** - Books, courses, training
- **Other** - Miscellaneous expenses

## 📊 Sample Expense Data

```json
{
  "id": 1,
  "description": "Weekly Groceries",
  "amount": 85.50,
  "category": "Food & Dining",
  "date": "2024-11-18",
  "createdAt": "2024-11-18T10:30:00Z",
  "updatedAt": "2024-11-18T10:30:00Z",
  "tags": ["weekly", "essential"]
}
```

## 🔐 Configuration

### Frontend Configuration
- Port: `4200` (default)
- API URL: `http://localhost:8080` (see `environment.ts`)

### Backend Configuration
- Port: `8080` (default)
- Logging Level: `INFO` (configurable)

### Application Properties

Edit `expense-tracker/src/main/resources/application.properties`:

```properties
# Server Configuration
server.port=8080
server.servlet.context-path=/

# Logging
logging.level.root=INFO
logging.level.com.evans=DEBUG

# CORS Configuration
spring.web.cors.allowed-origins=http://localhost:4200
```

## 🐛 Troubleshooting

### Frontend Won't Connect to Backend
- Ensure backend is running on `http://localhost:8080`
- Check CORS configuration in backend
- Check browser console for CORS errors
- Verify frontend is making requests to correct API URL

### Port Already in Use
- Change frontend port: `ng serve --port 4201`
- Change backend port: Update `server.port` in `application.properties`

### Dependencies Installation Issues
```bash
# Clear npm cache and reinstall
npm cache clean --force
npm install

# For Maven
mvnw clean
mvnw install
```

### Build Fails
```bash
# Frontend
cd Expense_tracker
npm run build

# Backend
cd expense-tracker
mvnw clean package
```

## 📈 Usage Tips

1. **Organize by Category** - Use meaningful categories for better expense tracking
2. **Regular Review** - Check your expense statistics monthly
3. **Use Tags** - Add tags to expenses for better organization
4. **Budget Planning** - Use statistics to plan your budget
5. **Backup Data** - Regularly backup your expense data

## 🤝 Contributing

### How to Contribute

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Code Standards

- Follow the existing code structure
- Write meaningful commit messages
- Add tests for new features
- Update documentation as needed
- Ensure tests pass before submitting PR

## 📝 Development Workflow

### Adding a New Expense Category

1. Update the backend `Expense` model to include the category
2. Create the category in the frontend
3. Add category to filter options
4. Update statistics calculations if needed
5. Write tests for the new category
6. Update documentation

### Adding a New Feature

1. Create a feature branch
2. Implement backend endpoint
3. Create frontend component/service
4. Connect frontend to backend
5. Add unit tests
6. Test end-to-end
7. Submit pull request

## 📄 License

This project is part of the modernization initiative.

## 👥 Author

Created by Evans

## 📞 Support

For issues and questions:
1. Check existing issues on GitHub
2. Create a new issue with detailed description
3. Include environment details and error logs
4. Provide steps to reproduce the issue

## 🔄 Version History

### Version 1.0.0
- Initial release
- Basic expense tracking functionality
- Expense categorization
- Statistics and reporting

## 🎓 Learning Resources

- [Angular Documentation](https://angular.dev)
- [Spring Boot Documentation](https://spring.io/projects/spring-boot)
- [REST API Best Practices](https://restfulapi.net/)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/)

---

**Last Updated:** November 2026
**Version:** 1.0.0
**Status:** Active Development
