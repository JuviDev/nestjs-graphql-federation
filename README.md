# NestJS GraphQL Apollo

## Installation

```bash
pnpm install
```

## Running the app

```bash
# development
$ pnpm run start

# watch mode
$ pnpm run start:dev
$ pnpm run start:dev users
$ pnpm run start:dev posts

# production mode
$ pnpm run start:prod
```

## Test

```bash
# unit tests
$ pnpm run test

# e2e tests
$ pnpm run test:e2e

# test coverage
$ pnpm run test:cov
```

## GraphQL

Open the browser and go to
<http://localhost:3002/graphql>

HTTP Headers for the requests

```json
{
  "Authorization": "123"
}
```

### Mutations

```bash
# Create User
mutation {
  createUser(
    createUserInput:{id: "123", email:"test@mail.com", password:"test" }){
    id
    email
    password
  }
}

# Create Post
mutation {
  createPost(createPostInput: { authorId: "123", id: "234" , body: "Text of the post"}){
    id
    authorId
    body
  }
}
```

### Queries

```bash
# Get all Users
query {
  users {
    id
    email
    password
    posts{
      id
      authorId
      body
    }
  }
}

# Get all Posts
query {
  posts {
    id 
    authorId
    body
    user{
      id
      email
      password
    }
  }
}
```
