### Building a Static Website on GitHub Pages Using Eleventy with a Contact Form via Fabform.io

This tutorial will walk you through creating a static website using the Eleventy static site generator and deploying it on GitHub Pages. Additionally, we'll set up a contact form using [Fabform.io](https://fabform.io/), a service that easily handles form submissions for static sites. 

By the end of this tutorial, you'll have a functional static website with a working contact form.

---

### Prerequisites

- **Git and GitHub account**: You'll need Git installed and a GitHub account. Sign up for a free account at [GitHub](https://github.com/).
- **Node.js and npm**: Install Node.js and npm from [here](https://nodejs.org/).
- **Basic knowledge of HTML/CSS**: This tutorial assumes you have basic knowledge of HTML and CSS.

---

### Step 1: Install Eleventy

Eleventy is a simple static site generator. To install it, you'll need to have Node.js and npm installed.

1. Open your terminal or command prompt.
2. Run the following command to install Eleventy globally:

   ```bash
   npm install -g @11ty/eleventy
   ```

3. Verify that Eleventy is installed by running:

   ```bash
   eleventy --version
   ```

   If installed correctly, you'll see the version number of Eleventy.

### Step 2: Create Your Project Directory

1. Create a directory for your project. Navigate to the location where you want to create your project and run:

   ```bash
   mkdir my-eleventy-site
   cd my-eleventy-site
   ```

2. Initialize a new Node.js project:

   ```bash
   npm init -y
   ```

3. Install Eleventy as a local dependency:

   ```bash
   npm install @11ty/eleventy --save-dev
   ```

4. Create a new directory for your site's content:

   ```bash
   mkdir src
   ```

5. Inside the `src` directory, create an `index.md` file:

   ```bash
   echo "# Hello World!" > src/index.md
   ```

### Step 3: Configure Eleventy

1. In the root of your project directory, create an `.eleventy.js` configuration file:

   ```bash
   touch .eleventy.js
   ```

2. Add the following configuration to the `.eleventy.js` file:

   ```javascript
   module.exports = function(eleventyConfig) {
     return {
       dir: {
         input: "src",
         output: "_site"
       }
     };
   };
   ```

   This configuration tells Eleventy to look for source files in the `src` directory and output the generated files to the `_site` directory.

### Step 4: Add HTML and CSS

1. Inside the `src` directory, create a new file called `index.html`:

   ```bash
   touch src/index.html
   ```

2. Add some basic HTML to the `index.html` file:

   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
     <meta charset="UTF-8">
     <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <title>My Eleventy Site</title>
     <link rel="stylesheet" href="/styles.css">
   </head>
   <body>
     <h1>Welcome to My Eleventy Site</h1>
     <p>This is a static website generated using Eleventy.</p>
     <a href="/contact.html">Contact</a>
   </body>
   </html>
   ```

3. Add a CSS file to style your site:

   ```bash
   touch src/styles.css
   ```

   Add some basic CSS:

   ```css
   body {
     font-family: Arial, sans-serif;
     margin: 0;
     padding: 20px;
   }

   h1 {
     color: #333;
   }
   ```

### Step 5: Create a Contact Page with Fabform.io

1. Create a new file called `contact.html` in the `src` directory:

   ```bash
   touch src/contact.html
   ```

2. Sign up for a free account on [Fabform.io](https://fabform.io/).

3. Once signed in, click on **"Create a New Form"**. 

4. Customize the form fields as needed. For example, you can add fields for "Name", "Email", and "Message".

5. After creating your form, you'll get an HTML snippet that looks something like this:

   ```html
   <form action="https://fabform.io/f/your-form-id" method="POST">
     <label for="name">Name:</label>
     <input type="text" id="name" name="name" required>

     <label for="email">Email:</label>
     <input type="email" id="email" name="email" required>

     <label for="message">Message:</label>
     <textarea id="message" name="message" required></textarea>

     <button type="submit">Send</button>
   </form>
   ```

6. Add this form to your `contact.html` file:

   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
     <meta charset="UTF-8">
     <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <title>Contact Us</title>
     <link rel="stylesheet" href="/styles.css">
   </head>
   <body>
     <h1>Contact Us</h1>
     <form action="https://fabform.io/f/your-form-id" method="POST">
       <label for="name">Name:</label>
       <input type="text" id="name" name="name" required>

       <label for="email">Email:</label>
       <input type="email" id="email" name="email" required>

       <label for="message">Message:</label>
       <textarea id="message" name="message" required></textarea>

       <button type="submit">Send</button>
     </form>
   </body>
   </html>
   ```

   Replace `"your-form-id"` with the actual form ID provided by Fabform.io.

### Step 6: Build and Test Your Site Locally

1. In your terminal, run the Eleventy build command:

   ```bash
   npx eleventy
   ```

2. This will generate your static site in the `_site` directory.

3. To serve your site locally, use Eleventy’s built-in development server:

   ```bash
   npx eleventy --serve
   ```

4. Open your browser and navigate to `http://localhost:8080`. You should see your site and be able to navigate to the contact page.

### Step 7: Deploy Your Site on GitHub Pages

1. Create a new repository on GitHub.

2. Initialize a Git repository in your project directory:

   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   ```

3. Add your GitHub repository as a remote:

   ```bash
   git remote add origin https://github.com/your-username/your-repo-name.git
   ```

4. Push your code to GitHub:

   ```bash
   git push -u origin master
   ```

5. Go to your repository on GitHub. Click on the "Settings" tab.

6. Scroll down to the **GitHub Pages** section. Under "Source", select the `master` branch and click "Save".

7. Your site will be deployed on GitHub Pages at `https://your-username.github.io/your-repo-name/`.

### Step 8: Test Your Contact Form

1. Navigate to the contact page of your live site.

2. Fill out the form and submit it. Fabform.io will handle the submission, and you should receive the details in your email (or in the Fabform.io dashboard, depending on your settings).

---

### Conclusion

Congratulations! You've successfully created a static website using Eleventy, deployed it on GitHub Pages, and added a functional contact form using Fabform.io. You now have a simple but powerful static site with a form that can handle submissions without requiring any backend code.

Feel free to customize your site further by exploring more of Eleventy’s features or enhancing your design with additional CSS or JavaScript.

If you encounter any issues or need further customization, refer to the following resources:

- **Eleventy Documentation**: [https://www.11ty.dev/docs/](https://www.11ty.dev/docs/)
- **Fabform.io Documentation**: [https://fabform.io/docs](https://fabform.io/docs)
- **GitHub Pages Documentation**: [https://pages.github.com/](https://pages.github.com/)

