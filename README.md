# 
Explanation
The main goal of this project was to build a Semester Registration System for Sherubtse College by applying the MVC structure and using Node.js, Express.js, PostgreSQL, and EJS. This stage concentrated on creating a safe way for users to log in and out, register, and verify their email addresses.

For the first phase, we set up and configured important npm packages, including express, pg, dotenv, bcryptjs, jsonwebtoken, and nodemailer. To achieve complete separation, a structuring based on the Model-View-Controller (MVC) approach was applied to the folder layout.

The user model is found in userModel.js, where the PostgreSQL table users was created using SQL queries. You’ll find data about users here such as id, username, email, password, role, is_verified, and verification tokens. Using environment variables in a db.js file helped secure and better manage the connection to the database.

The process of authenticating users lies in the authController.js file.
•	When you sign up, the password is stored as a hash (bcryptjs), and a verification token is also generated (jsonwebtoken).
•	Use of nodemailer allows an email to be sent to the user, with a verification link inside. The user’s is_verified data is changed once they have clicked on the confirmation link.
•	The system checks the credentials and verifies the email before allowing you to log in.
•	The system will send the user a special reset link via email to help them recover their password. Tapping this takes them to an entry page for resetting their password with a time-limited token.

EJS templates are used to create the frontend, giving different looks to the landing page, login, registration, forgot password, and password reset pages. HTML forms are made to send the user’s data to the corresponding routes. It helps ensure that all parts of the user interface have matching styles.

