Project Structure:
   blog-app-backend/
├── node_modules/
├── .env
├── package.json
├── server.js
├── db.js
├── routes/
│   ├── auth.js
│   └── posts.js
└── middleware/
    └── auth.js



  * Project Structure (simplified):
   blog-app-frontend/
├── node_modules/
├── public/
├── src/
│   ├── App.js
│   ├── index.js
│   ├── components/
│   │   ├── Header.js
│   │   ├── Footer.js
│   │   └── BlogCard.js
│   ├── pages/
│   │   ├── LoginPage.js
│   │   ├── SignupPage.js
│   │   ├── BlogListPage.js
│   │   ├── BlogDetailPage.js
│   │   └── CreateBlogPage.js
│   ├── services/
│   │   └── api.js
│   └── context/
│       └── AuthContext.js
├── package.json




SignupPage.js: Similar form to login, uses register from AuthContext.
 * BlogListPage.js:
   * Fetches posts from /api/posts using api.get('/posts?page=${page}&limit=${limit}').
   * Displays a list of BlogCard components.
   * Implements pagination controls.
 * BlogDetailPage.js:
   * Uses useParams to get the blog ID from the URL (/posts/:id).
   * Fetches a single post from /api/posts/:id.
   * Displays full title and content.
   * Includes edit/delete buttons if the logged-in user is the author (you'll need to pass user_id in the token or make an additional API call to check ownership).
 * CreateBlogPage.js:
   * Form for title and content.
   * Uses api.post('/posts', { title, content }) to create.
   * Accessible only via PrivateRoute.
 * EditBlogPage.js:
   * Similar to CreateBlogPage, but pre-fills the form with existing blog data.
   * Uses api.put('/posts/:id', { title, content, published }) to update.
   * Accessible only via PrivateRoute and only by the author.
Responsive Design:
 * Use CSS Flexbox or Grid for layouts.
 * Employ media queries for different screen sizes.
 * Consider using a UI library like Material-UI or Ant Design for pre-built responsive components, or a CSS framework like Bootstrap/Tailwind CSS. (Not included in snippets for brevity).
