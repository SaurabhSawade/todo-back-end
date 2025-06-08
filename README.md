# 📝 To-Do List API

This is a backend application for a To-Do List, built using **Node.js**, **Express.js**, and **MongoDB**. It provides RESTful APIs to create, read, update, and delete tasks.

---

## 📁 Project Structure
todo-list-app/
├── controllers/
│   └── taskController.js
├── models/
│   └── Task.js
├── routes/
│   └── taskRoutes.js
├── config/
│   └── db.js
├── .env
├── index.js
├── package.json
└── README.md


---

##  Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/todo-list-app.git
cd todo-list-app
npm install

npx nodemon index.js



🧠 Challenges Faced During Implementation

1. MongoDB Connection Issues

Challenge: Initially, I encountered errors while connecting to MongoDB using Mongoose, especially when switching between local MongoDB and MongoDB Atlas.

Solution:
	•	I created a separate config/db.js file to handle the connection logic.
	•	Used dotenv to store the MongoDB URI securely.
	•	Handled connection errors with proper try/catch and logged descriptive messages to quickly debug.

⸻

2. Handling Invalid or Missing Task IDs

Challenge: When trying to update or delete tasks using an invalid ID, the server responded with generic or unclear errors.

Solution:
	•	Implemented custom error handling using middleware.
	•	Added checks to validate ObjectId before performing operations using mongoose.Types.ObjectId.isValid(id).

⸻

3. Code Structure and Maintainability

Challenge: Managing all the logic in a single file quickly became unmanageable.

Solution:
	•	Refactored the code into a modular structure using controllers, routes, and models.
	•	This separation made the project cleaner, scalable, and easier to debug.

⸻

4. Data Validation

Challenge: Users could send incomplete or invalid task data (e.g., empty title, wrong date format).

Solution:
	•	Added Mongoose validation rules in the Task model.
	•	Returned detailed error messages to the client when validation failed.
	•	Plan to integrate Joi or express-validator for more robust validation in the future.

⸻

5. Testing APIs Without a Frontend

Challenge: Since there was no frontend initially, I had to manually test each route.

Solution:
	•	Used Postman and VSCode REST Client to test all endpoints.
	•	Created example request bodies to reuse during testing.