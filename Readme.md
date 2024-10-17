##TOGGLE FOR NAV-BAR


```react

import contact from "./contact/Contact"
import { Link } from 'react-router-dom'
import React, { useState } from 'react';
import './Navbar.css';
import myImage from '../Assets/logo.png';




const Navbar = () => {
  const [isOpen, setIsOpen] = useState(false);

  const toggleMenu = () => {
    setIsOpen(!isOpen);
  };

  return (
    <nav className="navbar">
      <div className="navbar-container">
        
         <div className='logo'>


          <img src={myImage} alt="no_logo" />


</div>
        <div className={`navbar-menu ${isOpen ? 'active' : ''}`}>
          <a href="/" className="navbar-item">Home</a>
          <a href="/services" className="navbar-item">Services</a>
          <a href="/about" className="navbar-item">About Us</a>
          <a href="/contact" className="navbar-item">Contact</a>
          <button type="button" class="btn btn-warning  fw-bold">DOWNLOAD APP</button>
        </div>
        <div className="navbar-toggle" onClick={toggleMenu}>
          <span className="bar"></span>
          <span className="bar"></span>
          <span className="bar"></span>
        </div>
      </div>
    </nav>
  );
};

export default Navbar;

```



```css
/* Basic styling */
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color:black;
  padding: 10px;
  font-weight: 800;
}

.navbar-container {
  display: flex;
  justify-content: space-between;
  width: 100%;
  align-items: center;
}

.logo img {
  width: 150px; /* Adjust the size of the logo */
}

.navbar-menu {
  display: flex;
  gap: 20px;
  transition: all 0.3s ease;
}

/* Default hidden state for menu on small devices */
.navbar-menu.active {
  display: flex;
  flex-direction: column;
  position: absolute;
  top: 60px; /* Adjust according to your navbar height */
  left: 0;
  right: 0;
  background-color: #333;
  padding: 20px;
  z-index: 1000;
}

.navbar-item {
  color: white;
  text-decoration: none;
  padding: 10px;
}

.navbar-item:hover {
  color: #ffa500;
}

/* Toggle button styling */
.navbar-toggle {
  display: none;
  cursor: pointer;
  flex-direction: column;
  justify-content: space-between;
  width: 30px;
  height: 20px;
}

.bar {
  height: 3px;
  width: 100%;
  background-color: white;
  margin: 3px 0;
}

/* Show the toggle button on smaller screens */
@media (max-width: 768px) {
  .navbar-menu {
    display: none;
  }

  .navbar-menu.active {
    display: flex;
  }

  .navbar-toggle {
    display: flex;
  }
}




```

---
---
---
