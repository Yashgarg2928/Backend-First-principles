# Backend-First-principles

### What is a backend? and what is its need?
Backend server is essentlly a central mushine that hace connection to all the clints and services. Its work is to handle all the services related to data and business logic.

### Why not use frontend for backend logic?
Frontend works basiclly when we call a url path it sends request to reverse proxy then that sends our frontend code to browser and that code will be runned in browser. which has limited resources. It has security issue as anyone can change frontend code in there browser. We can call apis from different domains.