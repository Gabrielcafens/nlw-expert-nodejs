Certainly! Below is a formatted README for your NLW Expert Node.js project. You can copy and paste this into your README.md file on GitHub:

```markdown
# NLW Expert (Node.js) - Real-time Voting System

This project implements a real-time voting system where users can create polls and others can cast their votes. The system generates a ranking among the options and updates the votes in real-time, providing instant feedback and engagement.

## Features

- **Create Polls:** Users can easily create polls with a title and multiple options.
- **Cast Votes:** Users can choose an option in a poll and submit their vote.
- **Real-time Updates:** Votes are reflected instantly in the results, displaying the current ranking of options.
- **WebSockets:** Utilizes WebSockets for efficient and bi-directional communication, ensuring seamless updates without refreshing the page.

## Technology Stack

- **Node.js:** JavaScript runtime environment for the backend server.
- **PostgreSQL:** Relational database for storing poll data and votes.
- **Redis:** In-memory data store for real-time caching and leaderboards.
- **Docker:** Containerization technology for streamlining deployment and scalability.

## Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Gabrielcafens/nlw-expert-nodejs.git
   cd nlw-expert-nodejs
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Set up database and cache:**
   - Install Docker: [Get Started with Docker](https://docs.docker.com/get-started/)
   - Start PostgreSQL and Redis with `docker-compose up -d`.

4. **Configure environment:**
   - Create a `.env` file from `.env.example` and add your database and Redis connection details.

5. **Run the application:**
   ```bash
   npm run dev
   ```

6. **Test it!**
   - Access the application in your browser: [http://localhost:3000](http://localhost:3000)
   - Create a poll, cast votes, and observe the real-time updates.

## API Endpoints

### Create a Poll

- **Method:** POST
- **Endpoint:** `/polls`
- **Request body:**
  ```json
  {
    "title": "Your poll title",
    "options": ["Option 1", "Option 2", ...]
  }
  ```
- **Response body:**
  ```json
  {
    "pollId": "unique_poll_id"
  }
  ```

### Get a Poll

- **Method:** GET
- **Endpoint:** `/polls/:pollId`
- **Response body:** Detailed poll data and vote information.

### Vote in a Poll

- **Method:** POST
- **Endpoint:** `/polls/:pollId/votes`
- **Request body:**
  ```json
  {
    "pollOptionId": "option_id"
  }
  ```
- **Response body:** None (success indicated by real-time update)

## WebSockets

Connect to `/polls/:pollId/results` for real-time vote updates.

- **Message:**
  ```json
  {
    "pollOptionId": "option_id",
    "votes": 2
  }
  ```

This README provides a starting point for understanding the NLW Expert Node.js project. Feel free to explore the code, contribute improvements, and build upon this foundation!
```

Make sure to replace placeholders like "Your poll title," "Option 1," etc., with the actual information from your application.
