# Meteora <a name="readme-top"></a>
![Static Badge](https://img.shields.io/badge/status-completed-green?style=for-the-badge)

## Table of Contents 
* [Title and Cover Image](#title-and-cover-image)
* [Badges](#badges)
* [Table of Contents](#table-of-contents)
* [Project Description](#project-description)
* [Features and Application Demonstration](#features-and-application-demonstration)
* [Project Access](#project-access)
* [Technologies Used](#technologies-used)
* [Project Developers](#project-developers)

## Project Description
Meteora is a dynamic e-commerce platform specializing in fashion products such as t-shirts, pants, sneakers, and jackets. Built with React, this application offers a rich user interface that allows customers to browse products, add them to their cart, and manage their purchases seamlessly. The project emphasizes efficient state management and clean code practices by incorporating advanced React features such as Context API and custom hooks.
<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Live Application
[Meteora Demonstration](https://meteora-three-tau.vercel.app)
<p align="right">(<a href="#readme-top">back to top</a>)</p>

 
## Features
- **Product Browsing**: Users can explore various fashion items available for purchase.
- **Interactive Shopping Cart**: Items can be added to the shopping cart by clicking on the cart icon. A dropdown menu displays the added items, allowing users to review their selections without navigating away from the current page.
- **Cart Management**:
  - **Add/Remove Products**: Users can increase or decrease the quantity of individual items directly from the dropdown cart.
  - **Delete Products**: Items can be removed entirely from the cart if desired.
  - **Checkout Process**: Clicking on 'Finalize Purchase' takes users to a dedicated shopping cart page, where they can see a detailed list of their products, adjust quantities, and see the total price.
- **State Management**:
  - **Prop Drilling Issue**: Initially, the application suffered from prop drilling, where states and functions were passed down multiple layers of components, complicating the codebase.
  - **Context API Integration**: To resolve the prop drilling, the Context API is used to provide a global state management solution, making states and functions directly accessible to components that need them without passing through intermediaries.
  - **Custom Hooks and useReducer**: Demonstrates the implementation of custom hooks to encapsulate component logic and the useReducer hook for managing state transitions more predictably compared to useState.
<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Project Access

### Prerequisites
- **Integrated Development Environment (IDE)**: Ensure you have your preferred IDE installed on your computer, such as Visual Studio Code or any other that supports JavaScript development.
- **Node.js**: Necessary for running the project. [Install Node.js here](https://nodejs.org/en/download/).

### Getting the Code
You can obtain the source code of the project in two ways:
- **Download ZIP**:
  - [Download the ZIP file here](https://github.com/victorhubarb/meteora/archive/refs/heads/main.zip). After downloading, unzip it on your computer and open the project in your IDE.
- **Clone via Git**:
  ```bash
  # Open your terminal (or command prompt)
  git clone https://github.com/victorhubarb/meteora.git
  
  # Navigate to the project directory
  cd meteora
<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Running the Project
Once you have the project setup, follow these steps to run the application:
- **Install Dependencies**:
  ```bash
  # Navigate to the project directory if you haven't already
  cd meteora
  
  # Install the necessary packages
  npm install

- **Start the Application**:
  ```bash
  npm start
 <p align="right">(<a href="#readme-top">back to top</a>)</p>
 

## Technologies Used
![Static Badge](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Static Badge](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![Static Badge](https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white)
<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Project Developers
| [<img loading="lazy" src="https://avatars.githubusercontent.com/u/80085116?v=4" width=115><br><sub>Victor Barbosa</sub>](https://github.com/victorhubarb) | [<img loading="lazy" src="https://avatars.githubusercontent.com/u/4975968?s=200&v=4" width=115><br><sub>Alura</sub>](https://github.com/alura-cursos) |
| :---: | :--: |
<p align="right">(<a href="#readme-top">back to top</a>)</p>
