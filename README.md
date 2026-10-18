<p align="center">
  <img alt="Polls" src=".github/banner.svg" width="400px"/>
</p>

<p align="center">
  <img alt="Repository size" src="https://img.shields.io/github/repo-size/rafaelfachinelli/polls?color=3498db&style=for-the-badge">
  <img alt="Last commit" src="https://img.shields.io/github/last-commit/rafaelfachinelli/polls?color=3498db&style=for-the-badge">
  <a href="https://rafaelfachinelli.com">
    <img alt="Developed by Rafael Fachinelli" src="https://img.shields.io/badge/Developer-Rafael_Fachinelli-3498db?style=for-the-badge">
  </a>
  <img alt="License" src="https://img.shields.io/badge/License-MIT-3498db?style=for-the-badge">
</p>

<p align="center">
  <a href="#information_source-about">About</a> •
  <a href="#memo-tasks">Tasks</a> •
  <a href="#arrow_forward-run">Run</a> •
  <a href="#hammer_and_wrench-technologies">Technologies</a> •
  <a href="#boy-author">Author</a> •
  <a href="#balance_scale-license">License</a>
</p>

---

## :information_source: About

🎭 A real-time poll API. Create a poll with options, vote, and follow the results live over WebSocket. Each voter is identified by a session cookie and can change the vote; the counts are kept in a Redis sorted set and published to the subscribers of the poll, while PostgreSQL (through Prisma) stores polls, options and votes.

Built in 2024 with Fastify.

---

## :memo: Tasks

<div align="center">
<details>
<summary>Click to view</summary>

|State|Task|
|:---:|:---|
|:heavy_check_mark:|Fastify server with Zod validation|
|:heavy_check_mark:|PostgreSQL and Redis with Docker Compose|
|:heavy_check_mark:|Prisma models and migrations: polls, options, votes|
|:heavy_check_mark:|Create a poll|
|:heavy_check_mark:|Get a poll with its vote counts|
|:heavy_check_mark:|Vote with a session cookie (and change the vote)|
|:heavy_check_mark:|Vote counts in Redis|
|:heavy_check_mark:|Live results over WebSocket (pub/sub)|

</details>
</div>

---

## :arrow_forward: Run

You need [Node.js](https://nodejs.org/) and [Docker](https://www.docker.com/). Create a `.env` with `DATABASE_URL` pointing to the PostgreSQL of `docker-compose.yml`.

```bash
# Start PostgreSQL and Redis
docker compose up -d

# Install dependencies and create the tables
npm install
npx prisma migrate dev

# Start the API in watch mode
npm run dev
```

> The API starts at <http://localhost:3333>.

<details>
<summary><b>API routes</b></summary>

|Method|Route|Description|
|:---:|:---|:---|
|POST|`/polls`|Create a poll with its options|
|GET|`/polls/:pollId`|Get a poll and its vote counts|
|POST|`/polls/:pollId/votes`|Vote on an option|
|WS|`/polls/:pollId/results`|Live results|

</details>

---

## :hammer_and_wrench: Technologies

<div align="center">

|Server|
|:---:|
|[Node.js](https://nodejs.org/)|
|[TypeScript](https://www.typescriptlang.org/)|
|[Fastify](https://fastify.dev/)|
|[Prisma](https://www.prisma.io/)|
|[PostgreSQL](https://www.postgresql.org/)|
|[Redis (ioredis)](https://github.com/redis/ioredis)|
|[Zod](https://zod.dev/)|
|[Docker Compose](https://docs.docker.com/compose/)|

</div>

---

## :boy: Author

<div align="center">

<a href="https://rafaelfachinelli.com">
  <img src="https://github.com/rafaelfachinelli.png" width="100px" alt="Rafael Fachinelli"/>
  <br/>
  <sub><b>Rafael Fachinelli</b></sub>
</a>

Tech Lead and software engineer. Get in touch!

[![Portfolio](https://img.shields.io/badge/-rafaelfachinelli.com-3498db?style=flat-square&logo=googlechrome&logoColor=white)](https://rafaelfachinelli.com)
[![LinkedIn](https://img.shields.io/badge/-Rafael_Fachinelli-0a66c2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rafaelfachinelli/)
[![GitHub](https://img.shields.io/badge/-rafaelfachinelli-000?style=flat-square&logo=github&logoColor=white)](https://github.com/rafaelfachinelli)
[![E-mail](https://img.shields.io/badge/-contato@rafaelfachinelli.com-3498db?style=flat-square)](mailto:contato@rafaelfachinelli.com)

</div>

---

## :balance_scale: License

This project is under the [MIT license](./LICENSE).
