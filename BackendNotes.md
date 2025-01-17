# 1 : Introduction

directory structure:

- src
  - index: Db connection
  - app : config,cookies,urlencode
  - constants: enums,DB name
- DB
- models
- controllers
- routes
- middleware
- utils
- more(depends upon framework/library)

# 2

**Hot reloading** is a powerful feature in React that allows you to see changes you make to your code reflected in the browser in real-time, without having to manually refresh the entire page. This significantly improves development efficiency, especially when you're working on UI components or making frequent tweaks to your code.

Here's how it works:

Hot reloading relies on a feature called Hot Module Replacement (HMR) provided by a module bundler like Webpack. HMR monitors your code for changes and, when it detects a modification, injects only the updated parts of the code into the running application.

# 3 connecting frontend and backend

**axios :** provides functionality for web requests.
provides production level features.

**CORS(Cross-Origin Resource Sharing) :** is a safety measure.

### npm cors

**What it does:**The cors library acts as a middleware for frameworks like Express or Connect. Middleware is like a special tool that can intercept requests and responses flowing through your application. In this case, the cors middleware inspects incoming requests and adds CORS headers to outgoing responses.

**Why use it?** By default, web browsers prevent websites from making requests to a different domain than the one they came from for security reasons. This can be a problem if you have a frontend application on one domain that needs to fetch data from an API on a different domain. The cors library helps you configure your server to allow these cross-origin requests.

### proxy

In a React project using Vite, a proxy acts as a middleman between your frontend code and a backend API on a different domain during development. It essentially "rewrites" requests made by your React application to point to the actual backend server location.

Here's how it works:

- Frontend Request: Your React application makes a request to an API endpoint, typically starting with something like /api/data.
- Proxy Intercepts: Vite's proxy configuration intercepts this request.
- Rewriting: The proxy rewrites the URL to point to the actual backend server location. For example, it might change /api/data to http://localhost:5000/api/data (assuming your backend is running on port 5000).
- Forwarding: The proxy then forwards the request to the rewritten URL on the backend server.
- Response: The backend server processes the request and sends a response.
  Back to Frontend: The proxy receives the response from the backend and delivers it back to your React application.

# 4: Data Modelling for backend with mongoose

import mongoose from "mongoose"
const userSchema= new mongoose.schema({//fields of userSchema} , {//timestamps:true})
export const User=mongoose.model("User",userSchema)

in mongoDB this will be saved as "users"
i.e. turns all characters into lower case and add a 's' in end.

visit this link : https://stackblitz.com/edit/stackblitz-starters-mg2tiy?file=models%2Ftodos%2Fuser.models.js

# 5: Ecommerce and Hospital management Data modelling

built data model for ecommerce and hospital

# 6 Project Setup

-**dev dependency** is the dependency that is used in development.(not in production)

# 7 Connecting Database in MERN

- In JavaScript, adding a semicolon ; before an Immediately Invoked Function Expression (IIFE) is a defensive practice to prevent potential issues with code concatenation or minification.

1. if an IIFE is placed immediately after a statement that doesn't end with a semicolon, the JavaScript engine might try to interpret the IIFE as part of the previous statement, leading to a syntax error.

2. Preventing Syntax Errors

Two important points about database connectivity:

1. When connecting to databases, handling potential data-not-found scenarios is essential. Employ try/catch blocks or promises to manage errors or we can also use promises.

- key to remember : ( wrap in try-catch )

2. Database operations involve latency, and traditional synchronous code can lead to blocking, where the program waits for the database query to complete before moving on. So, we should async/await which allows for non-blocking execution, enabling the program to continue with other tasks while waiting for the database response.

- key to remember : ( always remember the database is in another continent, so use async await)

- -r dotenv/config: This part of the script uses the -r (or --require) flag to require the dotenv/config module before running your application. The dotenv package is commonly used to load environment variables from a .env file, and dotenv/config loads these variables into process.env. By requiring dotenv/config in this way, it ensures that the environment variables are loaded before your application starts, making them available in your application code.

- --experimental-json-modules: This part enables support for ECMAScript (ES) Modules in your Node.js application, particularly support for .mjs files. ECMAScript Modules are a standard for organizing and importing JavaScript code, similar to CommonJS modules (.js files). This flag is used to enable support for using ES Modules in your Node.js project, as they are not enabled by default in all Node.js versions.

# 8 Custom API response and error handling

Installed following

- cookie-parser : performing CRUD operation on client's cookies
- cors : setting origin
-

(err,req,res,next)

**MiddleWare :** Jaane se phele mujhse milte jana \
MiddleWare functions in Express.js are often used to inspect, modify, or handle incoming requests and outgoing responses.
**Class Error :** for standardizing error handling. (basically what we are sending in json format while handling error such as success:true/false , error.message)

- can create custom error class by inheriting Class Error to handle custom errors.
- created ApiError.js for this

- created **Apiresponse.js** for streamlining and standardizing the api response.

**Error Status Code :**

- HTTP status codes are essential for communicating the outcome of an HTTP request. They provide crucial information about the success or failure of requests and help guide client-side applications in handling responses appropriately.

1. Informational responses (100 – 199)
2. Successful responses (200 – 299)
3. Redirection messages (300 – 399)
4. Client error responses (400 – 499)
5. Server error responses (500 – 599)

**A stack trace** is a report that provides information about the active stack frames at a particular point in time during the execution of a program. It is typically used for debugging purposes to help developers understand the sequence of function calls that led to an error or exception.

- basically error dikhayega

# 9 Models and JWT

- installed mongoose-aggregate for aggregation queries
- mongoose-aggregate-paginate-v2 helps you handle pagination for aggregation queries in MongoDB. It simplifies splitting large sets of data into pages, making it easier to work with and display results in a manageable way.

- bcryptjs for encrypting and decrypting passwords.
- jwt (json web token) for tokens.

- created model and methods

# 10 Multer : File Upload

production grade approach - uploading files on third party or another server e.g. aws,etc.

- packages used for file upload are : multer or express-fileUpload
- steps to upload

1. will get file using multer
2. store file temporarily in local server
3. upload on cloudinary

- package fs(filesystem) is used to manage the file system. this comes preinstalled with nodejs

# 11 HTTP Headers

**HTTP :** HyperText Transfer Protocol

**HTTP (Hypertext Transfer Protocol)** and **HTTPS (Hypertext Transfer Protocol Secure)** are both protocols used for transferring data over the web. Here’s a breakdown of their key differences:

- **HTTP**: Transmits data in plain text, which can be intercepted and read by anyone who has access to the data traffic between the client and server. This makes it less secure.
- **HTTPS**: Encrypts the data using SSL (Secure Sockets Layer) or TLS (Transport Layer Security) protocols. This encryption protects the data from being read or tampered with by unauthorized parties. It ensures the integrity and confidentiality of the information exchanged.

**HTTP Headers**

- **metadata :** data about the data.Key-Value pairs sent along with response and request.

- **Request Headers :** from client
- **Response Headers :** from server
- **Representation Headers :** encoding or compression
- **Payload Headers :** for data

### Most common Headers
1. **Accept**: Specifies the media types (e.g., text/html, application/json) that the client is willing to receive from the server.
2. **User-Agent:** Provides information about the client's browser or application making the request, often used for content negotiation and analytics.
3. **Authorization:** Contains credentials for authenticating the client with the server, typically used for accessing protected resources.
4. **Content-Type:** Indicates the media type of the resource being sent by the client (in the request body) or the type of the response content from the server.
5. **Cookie:** Sends stored cookies from the client to the server, which can be used for session management and personalization.
6. **Cache-Control:** Directs caching mechanisms on how to cache the response, specifying directives like no-cache or max-age.

### CORS
1. **Access-Control-Allow-Origin:** Specifies which domains are allowed to access the resources on the server. It can be a specific domain or * to allow all domains.
2. **Access-Control-Allow-Credentials:** Indicates whether the server allows credentials (like cookies or HTTP authentication) to be sent with the request. It must be set to true if the server allows credentials.
3. **Access-Control-Allow-Methods:** Lists the HTTP methods (e.g., GET, POST, PUT) that are permitted when accessing the resource. This header is used to define what methods are allowed in cross-origin requests.

### Security
1. Cross-Origin-Embedden-Policy 
2. Cross-Origin-Opener-Policy
3. Content-Security-Policy
4. X-XSS-Protection

### HTTP methods
Basic set of operations that can be used to interact With Server
1. GET : retrieve a resource
2. HEAD : No message body (response headers only)
3. OPTIONS : what operations are available
4. TRACE : loopback test (get same data)
5. DELETE : remove a resource
6. PUT : replace a re source
7. POST : interact with resource (mostly add)
8. PATCH : Change part of a resource

### HTTP Status Code
- 1xx Informational
- 2xx Success
- 3xx Redirection
- 4xx Client error
- 5xx Server error

### Informational (1xx)
- 100 Continue
- 102 Processing

### Success (2xx)
- 200 OK
- 201 Created
- 202 Accepted

### Redirection (3xx)
- 301 Moved Permanently
- 302 Found
- 303 See Other
- 304 Not Modified
- 307 Temporary Redirect
- 308 Permanent Redirect

### Client Error (4xx)
- 400 Bad Request
- 401 Unauthorized
- 402 Payment Required
- 403 Forbidden
- 404 Not Found
- 405 Method Not Allowed
- 408 Request Timeout

### Server Error (5xx)
- 500 Internal Server Error
- 501 Not Implemented
- 502 Bad Gateway
- 503 Service Unavailable
- 504 Gateway Timeout
- 505 HTTP Version Not Supported

# 12 Router and Controller
- Routes define the URL paths and HTTP methods (GET, POST, etc.) that the application will respond to.
- When an incoming request matches a route, it is directed to a specific controller function that handles the logic for that request.
- Routes focus on mapping URLs to the correct handler functions.
- Controllers focus on the business logic and processing of the request, such as interacting with the database, validating input, and preparing the response.

# 13 Register Controller 

# 14 Postman for Backend

# 15 Access Refresh Token, Middleware and cookies 

cookies are small pieces of data stored on the user's computer by the web browser while browsing a website.
- **httpOnly: true:** When a cookie is set with the HttpOnly attribute, it means that the cookie cannot be accessed or modified via JavaScript running on the client side. This helps prevent cross-site scripting (XSS) attacks, where a malicious script could potentially steal the cookie's data. By setting httpOnly: true, you ensure that the cookie is only accessible by the web server, which helps protect sensitive information, such as session tokens.

- **secure: true:** The Secure attribute ensures that the cookie is only sent over secure HTTPS connections, not HTTP. This helps prevent attackers from intercepting the cookie's data via man-in-the-middle (MITM) attacks. By setting secure: true, you ensure that the cookie is transmitted securely, thereby protecting it from being exposed to potential eavesdroppers.

# 16 Access and Refresh Token

- An **access token** is used to grant access to protected resources. It's a credential that a client application presents to a resource server to prove that the user has been authenticated and is authorized to access specific resources or perform certain actions.
-  Access tokens are usually short-lived. 

- A **refresh token** is used to obtain a new access token when the current access token expires. This allows the user to stay authenticated without having to log in again, improving user experience by avoiding frequent re-authentication.
- Refresh tokens have a longer lifespan compared to access tokens.

**Workflow**
1. Authentication: The user logs in, and the server issues an access token and a refresh token.
2. Access Resource: The client uses the access token to access protected resources.
3. Token Expiry: Once the access token expires, the client uses the refresh token to request a new access token.
4. New Tokens: The server issues a new access token (and possibly a new refresh token), and the client uses the new access token for subsequent requests.

# 17 Update controllers for user
- try to keep controllers separate whenever you are updating any file

# 18 Subscription Schema

# 19 MongoDB Aggregation Pipeline

Aggregation operations are expressions you can use to produce reduced and summarized results in MongoDB. MongoDB's aggregation framework allows you to create a pipeline that consists of one or more stages, each of which performs a specific operation on your data.

**Analogy**

You can think of the aggregation pipeline as similar to an automobile factory. Automobile manufacturing requires the use of assembly stations organized into assembly lines.

Each station has specialized tools, such as drills and welders. The factory transforms and assembles the initial parts and materials into finished products.

### The aggregation pipeline 
- aggregation pipeline is the assembly line, aggregation stages are the assembly stations, and expression operators are the specialized tools.
- An aggregation pipeline consists of one or more stages that process documents:
- Each stage performs an operation on the input documents. For example, a stage can filter documents, group documents, and calculate values.
- The documents that are output from a stage are passed to the next stage.
- An aggregation pipeline can return results for groups of documents. For example, return the total, average, maximum, and minimum values.
