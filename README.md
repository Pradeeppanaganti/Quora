# Quora REST CRUD App

A simple CRUD web application built with Node.js, Express, and EJS. It manages Quora-style posts with usernames and text content.

## Features

- View all posts
- Create a new post
- View an individual post
- Edit post content
- Delete posts
- Server-side rendered pages using EJS
- Method overriding for PATCH and DELETE form requests

## Requirements

- Node.js and npm

## Installation

1. Install the dependencies:

   ```bash
   npm install
   ```

2. Start the server:

   ```bash
   node index.js
   ```

3. Open the application at [http://localhost:8080/posts](http://localhost:8080/posts).

For automatic restarts during development, run the app with `nodemon` if it is installed globally:

```bash
nodemon index.js
```

## Routes

| Method | Route | Description |
| --- | --- | --- |
| GET | `/posts` | Display all posts |
| GET | `/posts/new` | Display the new-post form |
| POST | `/posts` | Create a post |
| GET | `/posts/:id` | Display one post |
| GET | `/posts/:id/edit` | Display the edit form |
| PATCH | `/posts/:id` | Update a post's content |
| DELETE | `/posts/:id` | Delete a post |

HTML forms use `method-override` with the `_method` query parameter to submit PATCH and DELETE requests.

## Project Structure

```text
.
├── index.js          # Express server and route definitions
├── package.json       # Project metadata and dependencies
├── public/
│   └── style.css      # Application styles
└── views/
    ├── edit.ejs      # Edit-post form
    ├── index.ejs     # Post listing
    ├── new.ejs       # New-post form
    └── show.ejs      # Individual post view
```

## Data Storage

Posts are stored in an in-memory array and are recreated with the initial sample data whenever the server restarts. No database is currently configured.

## Dependencies

- [Express](https://expressjs.com/) - Web framework
- [EJS](https://ejs.co/) - View engine
- [method-override](https://www.npmjs.com/package/method-override) - Support for PATCH and DELETE form submissions
- [uuid](https://www.npmjs.com/package/uuid) - Generate post IDs
