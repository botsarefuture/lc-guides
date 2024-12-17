## **LuovaClub Development Team Style Guide**

### **1. General Guidelines**

- **Code Readability**: Code should be easy to read, understandable, and maintainable. Write code as if the next person to read it is a developer who is unfamiliar with it.
- **Consistency**: Follow consistent naming conventions, indentation, and formatting across all projects to ensure uniformity.
- **Version Control**: Use Git for version control. All code should be committed regularly with clear, concise commit messages describing the changes made.
- **Comments**: Comment all non-trivial logic and any complex sections of code to explain the reasoning behind them. Keep comments up to date.

---

### **2. Code Formatting**

#### **2.1 Indentation**

- Use **2 spaces** for indentation (not tabs).
- Keep indentation consistent, even inside loops, conditionals, and functions.

#### **2.2 Line Length**

- **Maximum line length**: 80-100 characters.
- Break long lines into smaller, more readable chunks, especially when chaining method calls or writing strings.

#### **2.3 Naming Conventions**

##### **2.3.1 Variables**
- Use **camelCase** for variable names (`let userName = 'John';`).
- Avoid abbreviations or cryptic names. The name should clearly explain the purpose of the variable.

##### **2.3.2 Functions/Methods**
- Use **camelCase** for function names (`function calculateTotal() {}`).
- Name functions using verbs that describe their behavior (e.g., `calculateSum()`, `fetchData()`).

##### **2.3.3 Classes**
- Use **PascalCase** for class names (`class UserProfile {}`).
- Classes should be named after the object they represent.

##### **2.3.4 Constants**
- Use **UPPERCASE** with underscores for constants (`const MAX_LIMIT = 100;`).
- Constants should be declared at the top of the file or in a separate constants file for easier reference.

---

### **3. CSS and Design Guidelines**

#### **3.1 General Style Structure**

- Use **CSS variables** for colors, fonts, and spacing to ensure easy customization and consistency across the project.
- Avoid using inline styles; instead, create class-based styles for reusability.

#### **3.2 Colors**

- Define a base color palette in the `:root` selector for easy global access.
- Choose colors that are accessible to all users, ensuring good contrast for readability.

```css
:root {
    --primary-color: #1abc9c;
    --secondary-color: #34495e;
    --background-color: #2c3e50;
    --accent-color: #e74c3c;
    --text-color: #ecf0f1;
}
```

#### **3.3 Typography**

- Use **Roboto** as the base font. For headings, use **Roboto Slab** or another serif font for better emphasis.
- Avoid using too many fonts in one project. Stick to two fonts: one for the body and one for headings.
- Maintain a clear font hierarchy with appropriate sizes for headings, subheadings, and body text.

```css
body {
    font-family: 'Roboto', sans-serif;
    font-size: 16px;
    color: var(--text-color);
}

h1, h2, h3 {
    font-family: 'Roboto Slab', serif;
    font-weight: bold;
}
```

#### **3.4 Spacing and Layout**

- Use a consistent spacing unit, such as **8px**, to maintain rhythm and alignment in the design.
- Apply **flexbox** or **grid layout** for responsive, fluid layouts.

```css
.container {
    max-width: 1200px;
    margin: 20px auto;
    padding: 15px;
}
```

---

### **4. JavaScript (ES6+ Guidelines)**

#### **4.1 General Rules**

- Always use **const** for variables that do not change, and **let** for those that do.
- Use **arrow functions** for consistency and to avoid issues with the `this` keyword.

```javascript
const sum = (a, b) => a + b;
```

- Prefer **template literals** (`${variable}`) over string concatenation for better readability.

```javascript
let greeting = `Hello, ${userName}!`;
```

#### **4.2 Asynchronous Programming**

- Use **async/await** for asynchronous code instead of callbacks to maintain readability and avoid "callback hell."
- Always handle promise rejections and errors with proper error handling mechanisms like `try/catch` blocks.

```javascript
async function fetchUserData() {
    try {
        let response = await fetch('/user/data');
        let data = await response.json();
        return data;
    } catch (error) {
        console.error('Error fetching user data:', error);
    }
}
```

#### **4.3 Imports and Exports**

- Use **ES6 modules** for imports and exports.
- Group imports logically: external libraries first, then internal components or files.

```javascript
import React from 'react';
import { Button } from './components';
import { fetchData } from './utils';
```

---

### **5. HTML Structure**

#### **5.1 Semantic HTML**

- Use semantic HTML tags where possible (e.g., `<header>`, `<footer>`, `<nav>`, `<article>`, `<section>`).
- Ensure accessibility by using appropriate roles, `aria` attributes, and making sure interactive elements are keyboard-navigable.

#### **5.2 Accessibility**

- Ensure that all images have `alt` text describing the content.
- Use **form labels** and ensure that inputs are correctly associated with their labels via the `for` attribute.
- Test the web pages for WCAG compliance to ensure accessibility for users with disabilities.

```html
<label for="username">Username</label>
<input type="text" id="username" name="username" required>
```

#### **5.3 Form Validation**

- Always validate form data both client-side and server-side.
- Use custom validation messages to guide users when data is invalid.

---

### **6. Performance Optimization**

- **Minimize HTTP requests**: Combine CSS and JavaScript files, and use sprite sheets for images where possible.
- **Lazy load images** and other assets that are not immediately needed.
- **Optimize images**: Use appropriate image formats like WebP or SVG for vector-based images.
- **Use caching** effectively with cache-control headers.

---

### **7. Testing**

- Write unit tests for all critical code. Prefer **Jest** or **Mocha** for testing JavaScript.
- Use **Cypress** or **Selenium** for end-to-end testing of web applications.
- All tests should be written before coding the features (Test-Driven Development).

---

### **8. Security Practices**

- Always **sanitize user input** to prevent XSS (Cross-Site Scripting) attacks.
- Use **HTTPS** for all external communications, ensuring encrypted data transfer.
- Regularly update dependencies to avoid vulnerabilities.

---

### **9. Documentation**

- Maintain clear and concise documentation in markdown format (`README.md`).
- Document code functionality and provide examples for usage where applicable.
- Maintain changelogs (`CHANGELOG.md`) for all major changes to the project.

---

### **10. Collaboration and Code Reviews**

- All code should go through a **peer review process** before being merged into the main branch.
- Use **pull requests** for all changes and ensure that the PR description clearly outlines what changes have been made.
- Always leave constructive feedback and aim for collaboration rather than criticism.

---

### **11. Deployment and Hosting**

- **Automate deployment** with CI/CD pipelines (e.g., GitHub Actions, Jenkins).
- Use **Docker** containers for easy deployment and scalability.
- Ensure environments (development, staging, production) are configured consistently.

---

### **12. Tools and Environment**

- **Code Editor**: Use **VS Code** or any text editor with **Prettier** and **ESLint** configured.
- **Linters**: Set up **ESLint** for JavaScript and **stylelint** for CSS to ensure adherence to this style guide.
- **Prettier**: Automatically format code on save.

---

### **13. Flask Application Guidelines**

#### **13.1 Authentication and Security**

For authentication and security purposes, we use two key libraries in all Flask applications: **`flask_autosec`** and **`flask_lac`**.

##### **13.1.1 `flask_autosec` for Security**
- **`flask_autosec`** is used to automatically handle common security measures, such as:
  - Input validation
  - Protection against common vulnerabilities (e.g., XSS, CSRF)
  - Secure cookies
  - Secure headers (e.g., Content Security Policy, X-Frame-Options)
- To implement **`flask_autosec`**:
  - Ensure that all Flask apps are initialized with **`flask_autosec`** middleware to automatically apply security practices across the entire app.
  
  ```python
  from flask_autosec import AutoSec

  app = Flask(__name__)
  AutoSec(app)
  ```

- By integrating **`flask_autosec`**, we avoid manual implementation of security best practices for common web vulnerabilities and reduce the risk of security issues.

##### **13.1.2 `flask_lac` for Authentication**
- **`flask_lac`** provides a simple yet effective way to manage authentication and authorization within Flask applications.
- **`flask_lac`** integrates with your app to enable features such as:
  - User login and logout
  - Role-based access control
  - Token management (e.g., JWT)
  
To integrate **`flask_lac`**:
- First, install it via pip:

  ```bash
  pip install flask_lac
  ```

- Then, configure **`flask_lac`** in your Flask app as follows:

  ```python
  from flask_lac import LAC

  app = Flask(__name__)

  # Initialize LAC with app configuration
  lac = LAC(app)

  # Example: Use the `login_required` decorator to secure routes
  @app.route('/protected')
  @lac.login_required
  def protected():
      return "This is a protected page!"
  ```

- The **`login_required`** decorator ensures that only authenticated users can access certain routes, while **`lac`** handles user sessions, roles, and permissions.

#### **13.2 User Roles and Permissions**

When using **`flask_lac`**, it's essential to set up user roles and permissions carefully to ensure the app's security and access control.

##### **13.2.1 Role-Based Access Control (RBAC)**
- Define roles within your application (e.g., admin, user, guest) and assign them to users.
- Use **`lac.has_role()`** to protect routes and specify which roles can access specific resources.

  Example:
  ```python
  @app.route('/admin')
  @lac.login_required
  @lac.has_role('admin')
  def admin_page():
      return "Welcome, Admin!"
  ```

##### **13.2.2 Permissions**
- Permissions can be used to grant or restrict actions within specific routes.
- Assign permissions to roles and use **`lac.has_permission()`** to enforce them.

  Example:
  ```python
  @app.route('/edit')
  @lac.login_required
  @lac.has_permission('edit_post')
  def edit_post():
      return "You can edit this post."
  ```

#### **13.3 Session Management and Token Security**

- Use **`flask_lac`**’s built-in session management features to handle user sessions securely, and make sure that tokens (e.g., JWT) are stored securely (in HTTP-only cookies or headers).
- Always use secure cookie flags, especially when dealing with sensitive information like session tokens.

  ```python
  app.config['SESSION_COOKIE_HTTPONLY'] = True
  app.config['SESSION_COOKIE_SECURE'] = True  # Use HTTPS in production
  ```

#### **13.4 Login & Logout Flow**

- When a user logs in, create a session or issue a token for subsequent authentication checks. For logout, invalidate the session or token to ensure the user is logged out securely.

  Example login flow:
  ```python
  @app.route('/login', methods=['POST'])
  def login():
      username = request.form['username']
      password = request.form['password']
      user = User.authenticate(username, password)

      if user:
          lac.login(user)
          return redirect('/dashboard')
      else:
          return "Invalid credentials", 401
  ```

  Example logout flow:
  ```python
  @app.route('/logout')
  def logout():
      lac.logout()
      return redirect('/')
  ```

#### **13.5 Secure Password Handling**
- Use a secure method for password hashing and checking, such as **`werkzeug.security`** for password hashing and comparison.
- Ensure passwords are never stored in plaintext.

  ```python
  from werkzeug.security import generate_password_hash, check_password_hash

  hashed_password = generate_password_hash('mysecretpassword')
  if check_password_hash(hashed_password, 'mysecretpassword'):
      print("Password matches!")
  ```

---

By incorporating **`flask_autosec`** and **`flask_lac`**, all Flask applications within LuovaClub will follow best practices for both security and authentication, ensuring a secure environment for both users and data.


