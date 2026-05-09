# 🛒 InstaBasket - Professional Full-Stack Grocery Delivery Platform

**InstaBasket** is a state-of-the-art MERN ecosystem engineered for high-performance commerce. It features a sophisticated transaction engine, real-time inventory synchronization, and a multi-layered administration dashboard.

> This repository serves as a **technical showcase** of the platform's architecture and advanced feature set. The full production-ready source code is available for review upon request.

---

## 🚀 Key Technical Highlights

- **Atomic Transactions**: Leverages MongoDB sessions and transactions to ensure data integrity during complex checkout flows (inventory deduction + order creation + cart clearing).
- **Smart Idempotency**: Implements "Checkout Fingerprinting" (SHA-256) to prevent duplicate orders and Stripe session collision.
- **Dynamic Content Engine**: Fully-featured CMS allowing administrators to modify the frontend UI, theme icons, and promotional banners in real-time without code changes.
- **RBAC Architecture**: Strict Role-Based Access Control isolating User, Seller, and Admin data, with middleware-level authorization.
- **Resilient Payments**: Integrated with Stripe Checkout featuring session reuse, automatic tax calculation, and webhook-driven fulfillment.

---

## ✨ Advanced Feature Depth

### 🏪 Commerce & Inventory
- **Real-time Inventory Guard**: Automated stock monitoring that prevents overselling at the database level using atomic operators.
- **Stock Restoration Logic**: Automatically returns items to inventory if an order is cancelled or a payment session expires.
- **Advanced Tax Engine**: Configurable tax application per transaction.
- **Verified Reviews**: A multi-media rating system restricted to customers who have actually purchased and received the product.

### 🔐 Security & Reliability
- **HttpOnly Cookie Auth**: Secure JWT-based authentication preventing XSS-based token theft.
- **OTP Verification flow**: Email-based signup verification with temporary account state management.
- **Transaction Ledger**: Dedicated transaction models tracking payment intent IDs, refund statuses, and audit trails.
- **System Logging**: Winston-powered logger capturing critical events and transaction failures for debugging.

### 🛠️ Admin & Seller Operations
- **Interactive Analytics**: Time-series charts for revenue, order volume, and customer growth.
- **Refund Management**: One-click refund processing integrated directly with the Stripe API.
- **User Governance**: Granular account controls allowing admins to manage seller permissions and customer access.
- **Logistics Workflow**: Sophisticated order state machine (Pending → Processing → Shipped → Delivered) with strict transition rules.

---

## 🏗️ Technical Architecture

```text
InstaBasket/
├── client/                 # Vite + React 19 + Tailwind 4
│   ├── src/
│   │   ├── features/       # Domain-driven feature modules (Auth, Cart, Products)
│   │   ├── store/          # Zustand-powered global state slices
│   │   ├── shared/         # Reusable hooks, API clients, and constants
│   │   └── assets/         # Optimized media and branding assets
├── server/                 # Node.js + Express + MongoDB
│   ├── controllers/        # Domain logic (Orders, Admin, Webhooks)
│   ├── services/           # External API wrappers (Stripe, Refund Logic)
│   ├── utils/              # Inventory handlers, Loggers, Email services
│   ├── middlewares/        # RBAC, Validation, Security (CORS/Rate Limit)
│   └── models/             # Mongoose schemas with indexing for performance
```

---

## 🧑‍💼 System Roles (Interface Preview)

### 👤 **Customer Portal**
*High-performance catalog with smart search and secure checkout.*

| | | |
|:---:|:---:|:---:|
| ![User 1](https://github.com/user-attachments/assets/059ec843-b113-4c69-9acc-eeea9613a711) | ![User 2](https://github.com/user-attachments/assets/2e0fc8d9-88af-456b-b3ba-ee43fe9c2b99) | ![User 3](https://github.com/user-attachments/assets/c815b454-237a-4896-85f0-c932c9644db9) |
| ![User 4](https://github.com/user-attachments/assets/692931e1-d504-4e1f-bdb3-f55cad106e0d) | ![User 5](https://github.com/user-attachments/assets/465afba4-ea23-4d4e-a8e1-9c9052117235) | ![User 6](https://github.com/user-attachments/assets/56e9b2a3-e92f-495b-96bf-44041f42cc9c) |
| ![User 7](https://github.com/user-attachments/assets/8b8cf28e-3c75-48b2-907c-cd4cd018d812) | ![User 8](https://github.com/user-attachments/assets/0fc95435-301f-4847-b4e5-864bf63f056c) | |

### 🛍️ **Seller Ecosystem**
*Inventory management and multi-vendor order fulfillment.*

| | |
|:---:|:---:|
| ![Seller 1](https://github.com/user-attachments/assets/21e61462-7bdd-40ef-a7ec-722b22119943) | ![Seller 2](https://github.com/user-attachments/assets/f00faa2a-442b-41e3-b9b6-11311cc43c6d) |
| ![Seller 3](https://github.com/user-attachments/assets/107a8c77-dcc8-4547-9f70-2d315f309940) | ![Seller 4](https://github.com/user-attachments/assets/41f7deab-14cf-4614-8423-d0f1b75b0df8) |

### 🔐 **Admin Management Suite**
*Full platform oversight, financial auditing, and CMS control.*

| | |
|:---:|:---:|
| ![Admin 1](https://github.com/user-attachments/assets/2101a857-db96-43e5-9f42-d5b7f0b77885) | ![Admin 2](https://github.com/user-attachments/assets/8ce3dd5e-df14-4ec4-be73-57eacaac6f9f) |
| ![Admin 3](https://github.com/user-attachments/assets/243fdadc-cce4-412e-854e-a66b57fa1cd5) | ![Admin 4](https://github.com/user-attachments/assets/b17066a3-8617-4c34-a546-a1052c529d17) |
| ![Admin 5](https://github.com/user-attachments/assets/06bb1212-79a4-4703-a1e5-5e6882d6bf98) | ![Admin 6](https://github.com/user-attachments/assets/a3377e97-da21-4fdf-8534-204dab06e60c) |
| ![Admin 7](https://github.com/user-attachments/assets/7dc0b484-e155-46db-9fa3-b1be09b33e75) | |

---

## 🔧 Core Tech Stack

- **Frontend**: React 19, Vite, Tailwind CSS v4, Zustand, React Router v7, Framer Motion
- **Backend**: Node.js, Express.js, MongoDB + Mongoose, Zod Validation
- **Auth & Security**: JWT (HttpOnly), OTP Email, Google OAuth 2.0
- **Integrations**: Stripe Payments, Cloudinary Media, Nodemailer

---

## 🔗 Live Links

- **Live Demo**: [https://insta-basket.vercel.app](https://insta-basket.vercel.app)
- **Developer Portfolio**: [github.com/Akhileshpookkuttiyil](https://github.com/Akhileshpookkuttiyil)

---

## 📫 Contact & Inquiries

For professional inquiries or full source code access:

- **Email**: [akhileshpookkuttiyil@gmail.com](mailto:akhileshpookkuttiyil@gmail.com)
- **LinkedIn**: [Akhileshpookkuttiyil](https://www.linkedin.com/in/akhilesh-pookkuttiyil/)
