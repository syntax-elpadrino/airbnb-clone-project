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
