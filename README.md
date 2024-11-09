# DevTube

DevTube is a video-sharing platform that allows users to create, upload, and manage video content. This project is built using Node.js, Express, and MongoDB.

## Table of Contents

-   Installation
-   Usage
-   [Project Structure](#project-structure)
-   Routes
-   Middleware
-   Models
-   Controllers
-   License

## Installation

1. Clone the repository:

    ```sh
    git clone https://github.com/AnubhavMaithil/devtube.git
    cd devtube
    ```

2. Install dependencies:

    ```sh
    npm install
    ```

3. Create a [.env]() file in the root directory and add your environment variables:

    ```env
    DATABASE_URL=your_database_url
    SESSION_SECRET=your_session_secret
    ```

4. Start the development server:
    ```sh
    npm run dev
    ```

## Project Structure

```
.env
.gitignore
.hintrc
.vscode/
    settings.json
app.js
config.js
controllers/
    channelController.js
    commentController.js
    videoController.js
jsconfig.json
lib/
    db.js
    middlewares.js
    utils.js
models/
    Channel.js
    Comment.js
    Subscription.js
    Tag.js
    Video.js
package.json
public/
    css/
        devtube/
        studio/
        styles.css
    temp-upload/
routes/
    api.js
    channel/
        index.js
        videos/
    index.js
    studio/
        channel/
        index.js
    watch/
        index.js
views/
    404.ejs
    devtube/
    error.ejs
    studio/
```

## Routes

### API Routes

-   `GET /api/checkHandle`
-   `POST /api/updateStatus`
-   `GET /api/subscribe/:uid`
-   `GET /api/unsubscribe/:uid`
-   `GET /api/notification/:uid/:mode`

### Channel Routes

-   `GET /channel/:id`
-   `GET /channel/:id/videos`
-   `GET /channel/:id/shorts`

### Studio Routes

-   `GET /studio`
-   `GET /studio/videos`
-   `GET /studio/shorts`
-   `GET /studio/channel/:uid`
-   `GET /studio/channel/:uid/content`
-   `GET /studio/channel/:uid/analytics`
-   `GET /studio/channel/:uid/comments`
-   `GET /studio/channel/:uid/editing`

### Watch Routes

-   `GET /watch`
-   `GET /watch/react/:videoId`

## Middleware

-   `checkDBConnection`: Checks the database connection status.
-   `checkChannel`: Checks if a channel is created.
-   `isloggedIn`: Checks if a user is logged in.
-   `asyncHandler`: Utility function to handle async errors in middleware.

## Models

-   [Channel](/models/Channel.js) : Represents a channel.
-   [Comment](/models/Comment.js): Represents a comment.
-   [Subscription](/models/Subscription.js): Represents a subscription.
-   [Tag](/models/Tag.js): Represents a tag.
-   [Video](/models/Video.js) : Represents a video.

## Controllers

-   [channelController](/controllers/channelController.js) : Handles channel-related operations.
-   [commentController](/controllers/commentController.js)
    : Handles comment-related operations.
-   [videoController](/controllers/videoController.js) : Handles video-related operations.
