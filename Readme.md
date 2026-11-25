<div align="center">

# 🛍️ E-Commerce with AI Chatbot (Frontend)

**A modern, responsive eCommerce storefront built with React 19, Vite and Tailwind CSS, powered by an AI shopping assistant**

![React](https://img.shields.io/badge/React-19-61DAFB?logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-8-646CFF?logo=vite&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-4-06B6D4?logo=tailwindcss&logoColor=white)
![Redux Toolkit](https://img.shields.io/badge/Redux%20Toolkit-2-764ABC?logo=redux&logoColor=white)
![React Router](https://img.shields.io/badge/React%20Router-7-CA4245?logo=reactrouter&logoColor=white)

</div>

---

## 📖 Overview

This is the storefront of an AI-enhanced eCommerce platform. Shoppers can browse products, read **AI-analysed reviews**, chat with an **AI shopping assistant** and manage a persistent cart, all in a polished UI with light and dark themes.

It works together with the Spring Boot + Spring AI backend:
👉 **[ECommerceWithAIChatbotBackend](https://github.com/naveenrajput8823/ECommerceWithAIChatbotBackend)**

## ✨ Features

### 🛒 Shopping
- Landing page with an animated hero slider (Swiper) and a featured product grid
- Product details page with quantity selector, add-to-cart and ratings
- **Shopping cart** with quantity controls, subtotal, shipping fee and a free-shipping threshold
- Cart is **persisted in `localStorage`** and survives page reloads (Redux Toolkit)

### 🤖 AI-Powered
- **Floating AI chatbot** available on every page, with conversation memory handled by the backend
- **AI sentiment badges** on each review (Positive / Neutral / Negative) with confidence tooltip
- **"Customers say" card**: AI-generated summary of reviews grouped by aspects such as Quality, Size and Delivery
- Review submission with live validation feedback from the backend
- **AI image generation** page for sellers (`/seller/list-product`)

### 🎨 UI / UX
- Fully responsive layout
- **Light / Dark theme** that remembers your choice and respects system preference
- Smooth animations using Motion
- Toast notifications (React Toastify)
- Protected routes and a custom 404 page

### 🔐 Authentication (demo)
- Register and login forms built with React Hook Form
- Auth state through React Context and a custom `useAuth` hook
- Protected admin dashboard route

> ⚠️ Authentication is currently a **client-side demo**. Users are kept in memory and reset on page refresh. See the Roadmap.

## 🧰 Tech Stack

| Category        | Technology                          |
|-----------------|-------------------------------------|
| UI Library      | React 19                            |
| Build Tool      | Vite 8                              |
| Styling         | Tailwind CSS 4                      |
| Routing         | React Router 7                      |
| State           | Redux Toolkit, React Context        |
| Forms           | React Hook Form                     |
| HTTP            | Fetch API, Axios                    |
| Animation       | Motion                              |
| Carousel        | Swiper                              |
| Tables          | DataTables                          |
| Notifications   | React Toastify                      |
| Icons           | Lucide React                        |
| Linting         | Oxlint                              |

## 🔌 Backend Integration

| Feature              | Endpoint (backend)                       |
|----------------------|------------------------------------------|
| AI chatbot           | `POST /api/v1/openai/chat`               |
| Image generation     | `POST /api/v1/openai/generate-image`     |
| Fetch / add reviews  | `GET, POST /api/v1/reviews`              |
| "Customers say"      | `POST /api/v1/reviews/insights`          |

Product data is currently loaded from the public [Fake Store API](https://fakestoreapi.com).

## ✅ Prerequisites

- **Node.js 22 LTS** (or 20.19+)
- **npm**
- The [backend](https://github.com/naveenrajput8823/ECommerceWithAIChatbotBackend) running on `http://localhost:8080` (needed for chatbot, reviews and image generation)

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/naveenrajput8823/E-CommerceWithAIChatBot.git
cd E-CommerceWithAIChatBot
```

### 2. Install dependencies

```bash
npm install
```

### 3. Configure environment variables

Create a `.env` file in the project root (copy from `.env.example`):

```env
VITE_API_BASE_URL=http://localhost:8080
```

### 4. Start the development server

```bash
npm run dev
```

Open **http://localhost:5173**

> The backend allows requests from `http://localhost:5173` through CORS, so keep Vite on its default port.

## 📜 Available Scripts

| Command           | Description                       |
|-------------------|-----------------------------------|
| `npm run dev`     | Start the development server      |
| `npm run build`   | Create a production build         |
| `npm run preview` | Preview the production build      |
| `npm run lint`    | Lint the code with Oxlint         |

## 🗺️ Pages

| Route                  | Description                               |
|------------------------|-------------------------------------------|
| `/`                    | Landing page with hero slider and products |
| `/product/:prodId`     | Product details, reviews and AI insights  |
| `/cart`                | Shopping cart                             |
| `/login`               | Login                                     |
| `/register`            | Register                                  |
| `/about`               | About                                     |
| `/services`            | Services                                  |
| `/contact`             | Contact                                   |
| `/seller/list-product` | AI image generation for sellers           |
| `/dashboard/admin`     | Admin dashboard (login required)          |

## 🏗️ Project Structure

```
├── public
│   └── images/slides        # Hero slider images
├── src
│   ├── components           # ProductCard, Reviews, CustomersSay, FloatingChatbot, Navbar, Footer ...
│   ├── context              # AuthContextWrapper, ThemeContextWrapper
│   ├── hooks                # useAuth, useTheme
│   ├── pages                # LandingPage, Cart, Login, Register, About, Services, Contact
│   │   ├── admin            # Dashboard
│   │   └── seller           # ListProduct
│   ├── redux
│   │   ├── slices/Cart.js   # Cart state, selectors and actions
│   │   └── store.js
│   ├── Layout.jsx
│   ├── Router.jsx
│   └── main.jsx
├── docs                     # Learning notes and setup guides
├── .env.example
├── index.html
├── package.json
└── vite.config.js
```

## 🛣️ Roadmap

- [ ] Real authentication with the backend (password hashing, JWT / cookie sessions)
- [ ] Load products from the backend instead of the Fake Store API
- [ ] Checkout and order history
- [ ] Streaming (SSE) chatbot responses
- [ ] Role-based admin and seller dashboards
- [ ] Wishlist and product search / filters
- [ ] Unit and end-to-end tests
- [ ] Deployment (Vercel / Netlify)

## 📚 Learning Notes

React and Vite setup notes are available in the [`docs`](./docs) folder.

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m "Add your feature"`
4. Push to the branch: `git push origin feature/your-feature`
5. Open a Pull Request

## 👨‍💻 Author

**Naveen Rajput**

- GitHub: [@naveenrajput8823](https://github.com/naveenrajput8823)

---

<div align="center">

⭐ If you found this project useful, consider giving it a star!

</div>
