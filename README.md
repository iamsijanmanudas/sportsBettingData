# sportsBettingData
A web app for sports data analytics

### Project Outline

1. **Project Setup**
   - **Install WebStorm**: Download and install WebStorm from the JetBrains website.
   - **Create a New Project**: Open WebStorm and create a new project. Choose the relevant project type (e.g., "Empty Project" or "React App" if you are using React).

2. **Setup Version Control**
   - **Initialize Git Repository**: Initialize a Git repository for version control.
   - **Create a Repository on GitHub**: Create a new repository on GitHub and link it to your local repository.

3. **Project Structure**
   - **src**: Directory for source code.
   - **public**: Directory for static files like HTML.
   - **tests**: Directory for test files.
   - **package.json**: File to manage dependencies.

4. **Install Necessary Tools and Libraries**
   - **Node.js and npm**: Ensure Node.js and npm are installed.
   - **Frameworks/Libraries**: Depending on your choice, install the necessary frameworks/libraries.
     - For React: `npx create-react-app my-app`
     - For Vue: `npm install -g @vue/cli` and then `vue create my-app`
   - **HTTP Client**: Install Axios for API requests: `npm install axios`

5. **Create the Basic Structure**
   - **HTML File**: Create a basic HTML file in the public directory.
   - **App Component**: Create a main component (e.g., `App.js` in React or `App.vue` in Vue) to serve as the entry point.

6. **Fetching Data from the API**
   - **Create a Service**: Create a service file to handle API requests (e.g., `apiService.js`).
   - **Use Axios**: Use Axios to fetch data from the sports data API.

   ```javascript
   // apiService.js
   import axios from 'axios';

   const API_URL = 'https://api.sportsdata.io/v3/sports/scores/json/';

   export const fetchData = async (endpoint) => {
     try {
       const response = await axios.get(`${API_URL}${endpoint}`);
       return response.data;
     } catch (error) {
       console.error('Error fetching data', error);
     }
   };
   ```

7. **Displaying Data**
   - **State Management**: Use state management to handle the data (e.g., useState in React or reactive properties in Vue).
   - **Data Rendering**: Map the fetched data to components to display it on the webpage.

   ```javascript
   // App.js (React Example)
   import React, { useState, useEffect } from 'react';
   import { fetchData } from './apiService';

   function App() {
     const [data, setData] = useState([]);

     useEffect(() => {
       const getData = async () => {
         const result = await fetchData('endpoint');
         setData(result);
       };
       getData();
     }, []);

     return (
       <div>
         <h1>Sports Data</h1>
         <ul>
           {data.map(item => (
             <li key={item.id}>{item.name}</li>
           ))}
         </ul>
       </div>
     );
   }

   export default App;
   ```

8. **Comparing Data**
   - **Data Manipulation**: Write functions to compare and manipulate data as needed.
   - **Conditional Rendering**: Use conditional rendering to display comparison results.

9. **Styling**
   - **CSS Frameworks**: Use CSS frameworks like Bootstrap or Material-UI for styling.
   - **Custom Styles**: Write custom CSS or SCSS for specific styles.

10. **Testing**
    - **Unit Tests**: Write unit tests for your components using testing libraries like Jest.
    - **Integration Tests**: Ensure data fetching and rendering work correctly together.

11. **Deployment**
    - **Build the Project**: Create a production build of your project.
    - **Hosting**: Deploy the application to a hosting service like Netlify, Vercel, or GitHub Pages.

### Frameworks and Languages to Focus On
- **JavaScript**: The primary language for front-end development.
- **React or Vue.js**: Popular JavaScript frameworks for building user interfaces.
- **Node.js and npm**: For managing dependencies and running scripts.
- **Axios**: For making HTTP requests to the API.
- **CSS/SASS**: For styling your application.
- **Jest**: For testing JavaScript code.

### Learning Resources
- **JavaScript**: [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- **React**: [React Official Documentation](https://reactjs.org/docs/getting-started.html)
- **Vue.js**: [Vue.js Official Documentation](https://vuejs.org/v2/guide/)
- **Axios**: [Axios GitHub Repository](https://github.com/axios/axios)
- **CSS**: [CSS-Tricks](https://css-tricks.com/)
- **Jest**: [Jest Official Documentation](https://jestjs.io/docs/en/getting-started)

By following this outline, you'll be able to start your project, learn new skills, and effectively use WebStorm to develop your sports data web application.
