# MongoDB with .NET 

This solution demonstrates how to integrate MongoDB with a .NET 5 or .NET Core application using the official MongoDB C# driver. It provides a basic framework for performing CRUD operations on MongoDB collections through a RESTful API. The solution is structured into several key files that set up the MongoDB connection, define the controllers for handling HTTP requests, and configure the application startup.

## Program.cs

`Program.cs` is the entry point of the application. It performs the initial setup, including configuring the MongoDB client, registering services, and setting up middleware. Key components include:

- **MongoDB Client Configuration**: Establishes a connection to MongoDB using connection settings defined in the application's configuration (`appsettings.json`). It specifies the connection string and SSL settings.
- **Service Registration**: Registers the MongoDB client as a singleton service, making it available for dependency injection throughout the application.
- **Middleware Configuration**: Sets up essential middleware for the application, including routing, Swagger for API documentation, and HTTPS redirection.


## MongoDatabaseController.cs

`MongoDatabaseController.cs` provides a controller for database-level operations, allowing management of collections within the MongoDB database:

- **CreateCollection**: Creates a new collection within the database.
- **DropCollection**: Deletes a collection from the database.
- **ListCollections**: Lists all collections in the database.
- **RenameCollection**: Renames an existing collection.
- **GetCollection**: Get collection to interact with stringly typed class.


## MongoCollectionController.cs

`MongoCollectionController.cs` defines a controller that handles operations on a specific MongoDB collection, in this case, an Employee collection. It demonstrates how to perform various CRUD operations:

- **Create**: Adds a new Employee document to the collection.
- **CreateMany**: Inserts multiple Employee documents into the collection at once.
- **GetAll**: Retrieves all documents from the Employee collection.
- **GetById**: Fetches a single Employee document by its ID.
- **Replace**: Replaces an existing Employee document with a new one.
- **UpdateField**: Updates a specific field in an Employee document.
- **Delete**: Removes an Employee document from the collection.
- **EstimatedDocumentCount**: Gets an estimated count of documents in the collection.
- **CountDocuments**: Counts documents in the collection based on a filter.

## Endpoints

The solution exposes several RESTful endpoints through the `MongoDatabaseController` and `MongoCollectionController`:


### MongoDatabaseController Endpoints

- `POST /create-collection/{name}`: Creates a new collection.
- `DELETE /drop-collection/{name}`: Deletes a collection.
- `GET /list-collections`: Lists all collections in the database.
- `POST /rename-collection/{oldName}/{newName}`: Renames a collection.
- `GET /get-collection/{collectionName}`: Get collection to interact with stringly typed class.


### MongoCollectionController Endpoints

- `POST /create`: Creates a new Employee.
- `POST /create-many`: Inserts multiple Employee documents.
- `GET /all`: Retrieves all Employee documents.
- `GET /get-by-id/{id}`: Fetches an Employee by ID.
- `PUT /replace/{id}`: Replaces an existing Employee.
- `PATCH /update-field/{id}`: Updates a specific field of an Employee.
- `DELETE /delete/{id}`: Deletes an Employee by ID.
- `GET /count/estimated`: Gets an estimated document count.
- `GET /count`: Counts documents based on a filter.

## Setup and Configuration

To run this solution, ensure you have MongoDB installed and accessible either locally or through a cloud provider. Configure the connection string and other relevant settings in `appsettings.json`. After configuring, run the application and use the provided Swagger UI to interact with the API endpoints.
 