# Medium Clone

## Project Description

**Project Name:** Medium Clone

**Overview:**
The **Medium Clone** app is a web application designed to replicate the core features of the **Medium** platform, focusing on providing a space for users to create, read, and share articles. The app includes user authentication, article creation, and interaction with other users through comments and likes. It uses **React.js** for the frontend and **Appwrite** for backend services, including user management, data storage, and real-time updates.

The project aims to create an intuitive, clean, and responsive platform for blogging, allowing users to sign up, create and edit articles, and interact with other users’ content.

## Setup Instructions

### Pre-requisites:
- **Node.js** and **npm** installed on your system.
- **Appwrite** instance running with appropriate backend services configured.
- **Git** installed for version control.
- **Netlify** (or a similar platform) for deploying the frontend.

### Steps to Set Up the Project Locally:

1. **Clone the Repository:**
 git clone https://github.com/yourusername/medium-clone.git
 cd medium-clone
 
2.Install Dependencies: Run the following command to install all the necessary dependencies:
  npm install
   
3.Set Environment Variables: Create a .env file in the root of the project and add your Appwrite API credentials:
  REACT_APP_APPWRITE_ENDPOINT=<Your_Appwrite_Instance_Endpoint>
  REACT_APP_APPWRITE_PROJECT_ID=<Your_Project_ID>
  REACT_APP_APPWRITE_DATABASE_ID=<Your_Database_ID>
  REACT_APP_APPWRITE_COLLECTION_ID=<Your_Collection_ID>
  REACT_APP_APPWRITE_API_KEY=<Your_API_Key>

4. Run the Application Locally: To run the development server locally:
  npm start

6. Deploy the Application:
  Push your code to GitHub.
  Link the repository to Netlify for continuous deployment.

####Challenges Faced and How You Solved Them####

1. CORS Issues with Appwrite
   
  Challenge: When trying to make requests from the frontend to Appwrite’s backend, CORS errors prevented the connection.
  Solution: I updated the CORS settings in the Appwrite Console to allow the frontend domains (e.g., http://localhost:3000 for local 
  development and https://yourproject.netlify.app for production). This allowed the frontend to communicate properly with the backend.
  
3. Authentication and Role Management
   
  Challenge: Users could register successfully, but login failed with the error: User (role: guests) missing scope (account).
  Solution: I configured the roles and permissions properly in Appwrite, ensuring the "account" scope was granted to the user during 
  registration, thus allowing login and access to their account data.
  
5. Appwrite API Key Configuration
   
  Challenge: The app couldn’t connect to Appwrite during deployment due to missing or incorrect API keys.
  Solution: I created and used the correct API key with necessary permissions in the Appwrite Console. I then updated the environment 
  variables in the .env file, ensuring the correct credentials were available for the frontend to access Appwrite services.
  
7. Deployment Errors on Netlify
   
  Challenge: During deployment to Netlify, the build process failed due to missing dependencies and misconfigured environment variables.
  Solution: I ensured all required dependencies were listed in package.json, and environment variables were set up correctly in Netlify’s 
  build settings.
  
9. Appwrite Hostname Registration
    
  Challenge: Appwrite was rejecting requests from the frontend because I hadn’t registered the correct hostname.
  Solution: I went to the Appwrite Console, added the correct frontend domain (without the protocol, path, or port) under Hostname 
  Registration, and re-deployed the application. This resolved the issue with cross-origin requests.

  
  
