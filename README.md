# cs465-fullstack
CS-465 Full Stack Development with MEAN

Travlr Getaways – Full Stack Web Application

This project is a full stack web application built using the MEAN stack. It includes a customer-facing website and an administrative single-page application where trips can be created and updated. In the final version, secure login authentication was added to protect the admin side.

Architecture
Frontend: Express vs Angular

The customer side of the application uses Express with server-rendered HTML. When a user clicks on something, the request goes to the server, the server pulls data from MongoDB, builds the page, and sends the full HTML back to the browser.

The admin side is built as an Angular single-page application. Instead of reloading the entire page every time, Angular updates parts of the screen dynamically. It talks to the server through API endpoints and only pulls the data it needs.

The biggest difference is where the work happens. With Express, most of the work happens on the server. With Angular, more happens in the browser, and the server mainly handles data.

Why MongoDB?

MongoDB made sense because trip data fits naturally into a document structure. Each trip has related details like price, description, and images, and MongoDB handles that kind of structure well.

It also works smoothly with JavaScript. Since the entire stack uses JavaScript, passing data between layers feels consistent and straightforward.

Functionality
JSON vs JavaScript

JSON looks like JavaScript objects, but it’s just a data format. It doesn’t contain logic or functions. In this project, JSON is what connects everything together.

When Angular requests trip data, the server responds with JSON. Angular then takes that JSON and displays it using components. Without JSON, the frontend and backend wouldn’t be able to communicate cleanly.

Refactoring and Reusable Components

Throughout the project, I refactored code to make it cleaner and more efficient. For example, instead of repeating trip display code everywhere, I created a reusable TripCard component. That way, if I want to change how trips look, I only update it in one place.

I also moved API calls into a service instead of keeping them inside components. This keeps components focused on displaying data and makes the code easier to manage.

Reusable components make the app easier to maintain, easier to scale, and less repetitive.

Testing

Testing a full stack application means checking both the frontend and backend.

On the API side, I had to make sure endpoints returned the right data using the correct HTTP methods like GET and PUT. I also verified that the database updated correctly when data changed.

On the Angular side, I tested whether the SPA properly retrieved and displayed data. When things broke, I had to check multiple layers. Sometimes the issue was the API not running. Sometimes it was a routing problem. Sometimes it was a typo in a service.

When authentication was added, testing became more involved. I needed to confirm that login worked, that protected routes required credentials, and that unauthorized users could not modify data.

That process really showed how everything in a full stack app is connected.

Reflection

This course helped me understand how frontend and backend systems actually work together. Before this, they felt separate. Now I see how requests move through the entire stack.

I gained hands-on experience building RESTful APIs, creating an Angular SPA, working with MongoDB, handling asynchronous data, and implementing authentication. I also became much more comfortable debugging issues that span multiple layers of an application.

One of the biggest skills I developed was troubleshooting. When something didn’t work, I had to trace it from the browser to the API to the database. That experience made me more confident and more patient when solving technical problems.

Overall, this project gave me practical experience building and securing a full stack application. It strengthened both my technical skills and my ability to explain technical decisions clearly.
