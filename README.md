# ADRScenario1
ADR for scenario 1



ADR for Mobile App Development for Retail Company. 
This document outlines architectural decisions made by our group for the development of a new mobile app for a retail company, focusing on providing customers with products, browsing, purchasing capabilities, order tracking and loyalty program feature. Our aim to address the app's requirements, include offline mode, push notifications, payment gateway, user behaviour tracking, and image optimization. 


ADR 1: Choice of App Development Approach
status: Accepted

Context: The retail Company requires mobile app that supports both Android and iOS platforms, offering a seamless user experience with offline capabilities, and push notifications.    

Decision: After considering the trade-offs between native, web, and hybrid app development approaches, we decided to go with hybrid development using Flutter. This was influenced by Flutters ability to complie into native code, offereing high performance and its single codebase feature which simplifies app development and maintenance across Andriod and iOS. Flutter supports offline mode capabilities, integrates well with firebase for push notifications.

Consequences: Choosing Flutter enables faster development and easier maintenance due to single codebase approach. It may require additional effort to optimize performance to match that of native apps.   



ADR 2: UI Framework Selection 
status: Accepted

Context: apps success will be on engaging and responsive user interface that aligns with the retail companys brand image. 

Decision: Decided to use Material Design Framework within flutter for the UI design. Material design is comprehensive suite of design guidelines and components that ensures a consistent, intuitive and visually appealing user interface for both platforms. 

Consequences: Utilizing Material Design streamlines the UI development process, ensuring a consistent user experience that meets high usability standards. It limits customization to some extent, requiring additional work to implement unique desgin elements not covered by the framework. 




ADR 3: Backend Language Selection
status: Accepted

Context: The backend system needs to efficiently handle requests from the mobile app, process transactions, and manage user data securley.  

Decision: Node.js for the backend development. This decision was based on Node.js's non-blocking i/o model, which offeres efficient handling of concurrent requests, making it suitable for the apps expected workload. Vast ecosystem of libraries, such as Express for Api development, and its compatability with various databases and cloud services.  

Consequences: Using Node.js facilitates rapid development and easy integration with various services and databases. However, the asynchronous programming model of Node.js may introduce complexity in managing callback functions and promises. 



ADR 4: Permissions Strategy
status: Accepted

Context: The mobile app requires access to certain devices features and user data to function properly, including location for delivery tracking, and notifications for user engagment.  

Decision: Will implement a permissions strategy that requests permissions from users at runtime, specifically when the app needs to access the feature for the first time. This is guided by the best practices for privacy and user experience, ensuring transparency and building trust. 

Consequences: A runtime permissions strategy enhanves user trust by providing transparancy as to why and when the permissions are needed. It may howeve, interrupt the user experience if not implemented smoothly or if users decline permissions critical to the app's functionality. 



ADR 5:Data Storage Solution
status: Accepted

Context: Supporting offline mode and ensuring data consistency between the local app and the backend server are critical for the app's functionality.  

Decision: For Local data stroage, chose SQLite, which will be intrgrated with flutter through the use of the sqflite package. SQLite offers lightweight, file-based database solution that works well for storinguser data and product information on the device. For server side we will use MongoDB, a noSQL database for its flexibility in handling unstructured data, scalability and ease of integration with Node.js

Consequences: SQLite and MongoDB provide efficient data storage solutions that support the apps requirements for offline functionality and scalable server-side stroage. May require careful syncronization logic to ensure data consistency. 



ADR 6: Additional Frameworks and Technology Stacks
status: Accepted

Context: The apps diverse set of features, including payment processing, analytics, image optimization requires integration of additional frameworks and technologies.  

Decision: For payment integration, we will use paypal SDKs. Firebase will be used for analytics, push notifications and real-time database features. Cloudinary will be adopted for image optimization and storage and the app will utilize Flutters built-in localization support for multilanguage support.  

Consequences: Integrating these additional frameworks and technology stacks will enable a robust set of features and functionalities enhancing the user experience. It may increase the complexity of the apps architecture and require careful management of the interactions between different services. 



These decisions were made following a thorough analysis of the apps requirments and the available technological solutions. The goal was to design an architecture that is scalable, maintainable, and provides a seamless and engaging user experience. 
