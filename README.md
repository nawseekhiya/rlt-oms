# 🛒 Real-Time Order Management System

A full-stack application to create, view, and manage customer orders. Built with **Node.js (Express)** and **React.js**, integrated with **AWS (S3, DynamoDB, SNS)** and deployed using **GitHub Actions CI/CD**.

---

## 📌 Features

- 🌐 Full-stack app (React + Node.js)
- ☁️ AWS Integration:
  - DynamoDB for order data
  - S3 for storing PDF invoices
  - SNS for notifications on order creation
- 📥 File upload support (PDF invoices)
- 🔁 CI/CD pipeline with GitHub Actions
- 📊 Responsive UI with dashboard and analytics
- 📄 RESTful APIs with Swagger documentation

---

## 🧰 Tech Stack

### Frontend
- React.js
- Tailwind CSS / Bootstrap / Material UI
- Axios

### Backend
- Node.js (Express.js)
- Multer (PDF file handling)
- AWS SDK v3

### Cloud & DevOps
- AWS S3, DynamoDB, SNS
- GitHub Actions (CI/CD)

---

## 🗂️ Project Structure

```
rlt-oms/
├── order-service/             # Node.js backend
│   ├── controllers/
│   ├── routes/
│   ├── services/              # AWS SDK wrappers
│   ├── utils/
│   ├── app.js
│   └── server.js
│
├── order-ui/                  # React frontend
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/          # API calls
│   │   └── App.jsx
│
├── .github/
│   └── workflows/
│       └── deploy.yml         # CI/CD pipeline
│
├── BRANCHING.md               # Branching strategy
└── README.md
````

---

## 🧪 API Reference

### Base URL: `http://localhost:5000`

| Method | Endpoint       | Description                          |
|--------|----------------|--------------------------------------|
| POST   | `/orders`      | Create new order + upload invoice    |
| GET    | `/orders`      | Get all orders                       |
| GET    | `/orders/:id`  | Get single order by ID               |

### Sample Order Object:

```json
{
  "orderId": "123e4567-e89b-12d3-a456-426614174000",
  "customerName": "Jane Doe",
  "orderAmount": 500,
  "orderDate": "2025-08-02T12:34:56.000Z",
  "invoiceFileUrl": "https://s3.amazonaws.com/bucket/invoice.pdf"
}
````

---

## ⚙️ AWS Setup

### 🔸 DynamoDB

* Table: `orders`
* Primary Key: `orderId` (String)

### 🔸 S3

* Bucket: `ordique-invoices`
* Public access for files or use signed URLs

### 🔸 SNS

* Topic: `order-creation-topic`
* Add an email subscription for notifications

---

## 🔐 Environment Variables (`.env`)

Create a `.env` file inside `/order-service`:

```env
AWS_REGION=us-east-1
AWS_ACCESS_KEY_ID=your-access-key
AWS_SECRET_ACCESS_KEY=your-secret-key
S3_BUCKET_NAME=ordique-invoices
DYNAMODB_TABLE_NAME=orders
SNS_TOPIC_ARN=arn:aws:sns:us-east-1:123456789012:order-creation-topic
PORT=5000
```

---

## 🚀 Running Locally

### 📦 Backend (order-service)

```bash
cd order-service
npm install
npm run dev
```

### 🌐 Frontend (order-ui)

```bash
cd order-ui
npm install
npm run dev
```

---

## 🌀 CI/CD – GitHub Actions

The `.github/workflows/deploy.yml` file handles:

* Checkout repo
* Node.js install & build
* Run tests (if any)
* Deploy backend to AWS (EC2 / Elastic Beanstalk)

> 🧠 Pro Tip: Set up secrets (AWS keys, host) under GitHub repo settings → Secrets.

---

## 📄 Swagger UI

> Available at: `http://localhost:5000/api-docs`

To enable:

* Use `swagger-jsdoc` and `swagger-ui-express` in backend
* Define Swagger config in `swagger.js`

---

## 🎯 Bonus Features

* ✅ JWT Authentication
* 📤 Export order logs to S3 as JSON
* 📈 Dashboard chart using `chart.js` for order trends

---

## 📚 Documentation

This repo includes:

* ✅ Clean folder structure
* ✅ RESTful API documentation
* ✅ Frontend/backend run instructions
* ✅ CI/CD integration
* ✅ AWS resource mapping
* ✅ **[Branching Strategy](./BRANCHING.md)**

---

## 🧼 Code Quality

* ESLint/Prettier configuration (optional)
* Meaningful naming
* Centralized services/utilities
* Modular components

---

## 📋 Deliverables

* `order-service/` – Backend with REST APIs
* `order-ui/` – React frontend with routing
* `.github/workflows/deploy.yml` – CI/CD config
* `README.md` – This documentation
* Swagger, Analytics Chart, JWT

---

## 👨‍💻 Author

**Abhishek Mohanty**
🔗 [LinkedIn](https://linkedin.com/in/iamabhishekmohanty)

---