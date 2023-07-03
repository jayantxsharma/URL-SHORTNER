# URL-SHORTNER
It imports the required modules: shortid, URL model, and the necessary controller functions.

The handleGenerateNewShortURL function handles the generation of a new short URL. It validates the request body for the url field and generates a new short ID using the shortid package. It then creates a new URL document in the MongoDB database using the URL.create method.

The handleGetAnalytics function retrieves the analytics for a specific short URL. It finds the URL document based on the shortId parameter and returns the total clicks and visit history.

The urlSchema defines the structure of the URL documents in MongoDB using Mongoose. It includes fields for shortId, redirectURL, and visitHistory, which is an array of timestamp objects.

The URL model is created using the urlSchema.

The router is created using express.Router().

The handleGenerateNewShortURL function is assigned to the POST / route, which generates a new short URL.

The handleGetAnalytics function is assigned to the GET /analytics/:shortId route, which retrieves the analytics for a specific short URL.

The router is exported.

The connectToMongoDB function connects to the MongoDB database using the provided URL.

The connectToMongoDB function is exported.

The main Express application is created.

The connectToMongoDB function is called to establish a connection to the MongoDB database.

Middleware is added to parse JSON requests.

The urlRoute is mounted at the /url path.

A GET request handler is defined for /:shortId, which retrieves the long URL associated with the short ID and redirects the user to that URL. It also updates the visit history of the URL document in the database.

The server starts listening on the specified port, and a message is logged to the console when the server is started.

This code sets up an API for generating short URLs, retrieving analytics, and redirecting users to the original URLs based on the short IDs. It uses Express.js for routing and handling requests, Mongoose for connecting to MongoDB and defining models, and the shortid package for generating unique short IDs.
