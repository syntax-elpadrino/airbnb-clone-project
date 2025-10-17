# airbnb-clone-project
This project is a full-stack clone of the popular accommodation booking platform AirBnB. The goal is to build a functional web application that allows users to browse property listings, view detailed property information, and complete bookings. The project will cover frontend development, backend APIs, database design, and deployment.

## Project Goals
- Recreate key functionalities of Airbnb
- Learn modern web development practices
- Practice full-stack application architecture
- Implement user authentication and secure checkout

### Key Features
- **Property search and filtering**: Allow users to search for properties by location, price, and other filters.
- **Detailed property viewing**: Enable users to view detailed descriptions, photos, and availability.
- **Secure checkout process**: Implement a secure payment gateway and booking confirmation.
- **User authentication**: Enable account creation, login, and session management.

## Technology Stack

### Frontend
- **Languages:** HTML, CSS, JavaScript  
- **Framework:** React
- **Styling:** Tailwind CSS / SCSS  
- **Design Tool:** Figma
  
### Backend
- **Framework:** Django (Python) or Node.js (Express)  
- **Database:** MySQL / MongoDB / PostgreSQL  
- **API Layer:** RESTful APIs and GraphQL  
- **Authentication:** JWT  
- **Containerization:** Docker  
- **CI/CD:** GitHub Actions
  
## UI/UX Design Planning
### Planned Components
#### Navbar
- Logo  
- Search bar  
- User menu / profile dropdown  
- Mobile-friendly navigation  
#### Property Card
- Image  
- Price, location, and rating  
- Favourite button  
- Responsive grid layout  
#### Footer
- Links (About, Contact, Terms)  
- Company information  
- Social media icons  
- Copyright  

Each component will be reusable, accessible, and consistent across the app.

## Figma Design Specifications
### Color Styles
- **Primary:** #FF5A5F  
- **Secondary:** #008489  
- **Background:** #FFFFFF  
- **Text:** #222222  
- **Secondary Text:** #717171  

### Typography
- **Primary Font:** Circular, Medium (500), 16px  
- **Headings:** Circular, Bold (700), 24px–32px  
- **Secondary Text:** Circular, Book (400), 14px  

### Importance of Design Properties
Defining color and typography upfront ensures brand consistency and accessibility. It helps developers and designers maintain alignment across all components and devices.

## Team Roles and Responsibilities

### Project Manager
- **Responsibilities**: Oversees timeline, coordinates the team, and manages deliverables to ensure timely completion of project milestones.

### Frontend Developers
- **Responsibilities**: Implements UI components, ensures responsive design, and collaborates on frontend logic with backend developers.

### Backend Developers
- **Responsibilities**: Builds APIs, manages the database, implements business logic, and ensures scalability.

### Designers
- **Responsibilities**: Creates mockups, maintains design system, ensures UX quality, and collaborates with frontend developers to implement designs.

### QA/Testers
- **Responsibilities**: Writes test cases, performs testing, reports bugs, and ensures product quality.

### DevOps Engineers
- **Responsibilities**: Manages deployment, CI/CD pipeline, and server infrastructure to ensure smooth delivery and scalability.

### Product Owner
- **Responsibilities**: Defines requirements, prioritizes features, and represents stakeholders’ needs in the development process.
  
### Scrum Master
- **Responsibilities**: Facilitates agile processes, removes blockers, and organizes meetings to ensure smooth team collaboration.

## UI Component Patterns

### Planned Components

#### Navbar
- **Components**: Logo, Search bar, User navigation, Responsive menu
- **Responsiveness**: Ensures mobile and tablet compatibility

#### Property Card
- **Components**: Property image, Basic details (price, location, rating), Favorite button
- **Responsiveness**: Grid layout with cards rearranged based on screen size

#### Footer
- **Components**: Site links, Company information, Social media links, Copyright information
- **Responsiveness**: Stacked layout for small screens

Each component will be designed for reusability and consistency across the application.

## 🗃️ Database Design

### Entities and Relationships

Below is an overview of the main entities and how they relate to one another in the system.

---

## **1. Users**

**Fields:**

* `id` – Unique identifier (Primary Key)
* `name` – Full name of the user
* `email` – Unique email for login
* `password_hash` – Encrypted password
* `role` – Defines whether the user is an admin, host, or guest

**Relationships:**

* A **User** can list multiple **Properties**
* A **User** can make multiple **Bookings**
* A **User** can leave multiple **Reviews**

---

## **2. Properties**

**Fields:**

* `id` – Unique identifier (Primary Key)
* `title` – Name or headline of the property
* `description` – Detailed information about the property
* `price_per_night` – Cost per night
* `user_id` – Foreign Key linking to the property owner (User)

**Relationships:**

* A **Property** belongs to one **User**
* A **Property** can have many **Bookings**
* A **Property** can receive multiple **Reviews**



## **3. Bookings**

**Fields:**

* `id` – Unique identifier (Primary Key)
* `user_id` – Foreign Key (Guest making the booking)
* `property_id` – Foreign Key (Property being booked)
* `check_in_date` – Start of stay
* `check_out_date` – End of stay

**Relationships:**

* A **Booking** belongs to one **User**
* A **Booking** belongs to one **Property**
* A **Booking** can have one **Payment**

---

## **4. Reviews**

**Fields:**

* `id` – Unique identifier (Primary Key)
* `user_id` – Foreign Key (Reviewer)
* `property_id` – Foreign Key (Reviewed property)
* `rating` – Numeric rating (1–5)
* `comment` – Text feedback

**Relationships:**

* A **Review** belongs to one **User**
* A **Review** belongs to one **Property**

---

## **5. Payments**

**Fields:**

* `id` – Unique identifier (Primary Key)
* `booking_id` – Foreign Key (Linked Booking)
* `amount` – Total amount paid
* `payment_method` – e.g., card, PayPal, M-Pesa
* `status` – Payment status (pending, completed, failed)

**Relationships:**

* A **Payment** belongs to one **Booking**



## **Summary of Relationships**

* **User ↔ Property:** One-to-Many
* **User ↔ Booking:** One-to-Many
* **Property ↔ Booking:** One-to-Many
* **Property ↔ Review:** One-to-Many
* **Booking ↔ Payment:** One-to-One

## Feature Breakdown
### 1. User Management

- This feature handles all user-related functionality, including registration, authentication, and profile management. It ensures secure access using JWT authentication, allowing users to sign up, log in, and manage their personal details and booking history.

## 2. Property Management

Hosts can list, edit, and delete their properties through this module. Each property includes details such as title, description, location, price, images, and amenities. This feature makes it easy for property owners to manage their listings efficiently.

## 3. Booking System

This feature enables users to reserve available properties for specific dates. It includes date selection, price calculation, and confirmation of reservations. Each booking links the user to a property, creating a unique transaction record that tracks availability and prevents double-booking.

## 4. Payment Integration

The payment feature allows users to securely pay for their bookings using integrated payment gateways. It tracks transaction status, ensures data encryption, and provides receipts for each confirmed booking. This adds trust and financial accountability to the platform.

## 5. Review and Rating System

After completing a stay, users can leave reviews and rate properties based on their experience. This feature helps maintain transparency and trust, allowing future guests to make informed decisions based on previous feedback.

## 6. Search and Filtering

Users can search for properties using filters such as location, price range, amenities, and ratings. This feature improves user experience by helping them quickly find listings that match their preferences and budget.

## 7. Responsive UI/UX

The frontend design ensures the platform works seamlessly across devices — desktop, tablet, and mobile. This feature prioritizes accessibility, speed, and usability, making navigation simple and enjoyable for all users.

## API Security
### 1. Authentication

The system uses JWT (JSON Web Token) authentication to verify user identities before granting access to protected routes. Each token is unique to a user session and prevents unauthorized access. This ensures that only verified users can perform sensitive operations like booking a property or managing listings.

### 2. Authorization

After authentication, role-based authorization ensures that users can only access resources that match their permissions. For example, guests can make bookings, while hosts can add or edit property listings. This separation of privileges helps maintain data integrity and prevents misuse of the system.

### 3. Rate Limiting

To prevent API abuse and denial-of-service (DoS) attacks, rate limiting is implemented. It restricts the number of requests a user or IP address can make in a specific time frame, protecting the system from overload and ensuring fair usage among all users.

### 4. Data Encryption

Sensitive data such as passwords and payment details are encrypted both in transit and at rest. Using HTTPS (SSL/TLS) ensures secure data transfer, while encryption algorithms protect information stored in the database. This prevents unauthorized access even if data is intercepted or breached.

### 5. Input Validation & Sanitization

All API inputs are validated and sanitized to prevent common vulnerabilities like SQL injection, XSS (Cross-Site Scripting), and CSRF (Cross-Site Request Forgery). This ensures that the backend processes only safe and properly formatted data.

### 6. Secure Payment Handling

Payment endpoints are integrated with secure, third-party gateways that follow PCI-DSS compliance standards. This adds an extra layer of protection for financial transactions and user payment information.

### Why API Security is Crucial

- Protecting User Data: Prevents unauthorized access to personal details like emails, passwords, and addresses.

- Securing Financial Transactions: Ensures that all payment-related activities remain private and tamper-proof.

- Maintaining System Reliability: Reduces downtime and safeguards the platform from attacks or data corruption.

- Building User Trust: A secure application increases confidence and encourages long-term platform use.

## CI/CD Pipeline
### 1. What is CI/CD?

CI/CD (Continuous Integration and Continuous Deployment) is a development practice that automates the process of testing, building, and deploying applications. It ensures that code changes are automatically integrated, tested, and delivered to production efficiently and reliably.

### 2. Importance of CI/CD in This Project

Implementing CI/CD in the Airbnb Clone project improves development speed, collaboration, and product reliability.

Continuous Integration (CI): Automatically tests and integrates new code changes into the main branch to catch bugs early.

Continuous Deployment (CD): Ensures new features and fixes are quickly and safely deployed to production without manual intervention.
Together, they reduce errors, maintain consistent code quality, and provide a smooth user experience during updates.

### 3. Tools Used

GitHub Actions: Automates workflows such as running tests, linting, and deploying code directly from the repository.

Docker: Provides consistent development and deployment environments through containerization.

Docker Compose: Simplifies managing multi-service environments like frontend, backend, and database containers.

CI/CD Pipeline Example:

Developer pushes code to GitHub →

GitHub Actions runs tests automatically →

If all tests pass, Docker builds the image →

The new version is deployed to the server or cloud environment.

### 4. Benefits

Reduces human error through automation

Speeds up feature delivery and updates

Enhances team collaboration and transparency

Ensures every deployment is stable, tested, and consistent
