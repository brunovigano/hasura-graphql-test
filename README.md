# How to run

1. `docker-compose up -d` to run Hasura GraphQL engine & Postgres.
2. Head to `http://localhost:8080/console` to open the Hasura console.
3. Head to the [Hasura](http://localhost:8080) console, navigate to Data -> Create table and create a sample table called `profile` with the following columns:

```sdfds
profile (
  id INT PRIMARY KEY,
  name TEXT
)
```

![alt text](https://docs.hasura.io/1.0/_images/create-profile-table1.png 'query data')

4. Head to the `GraphiQL` tab in the console select `+ADD NEW MUTATION` and try running the following query:

```
mutation MyMutation {
  insert_profile(objects: {name: "José", id: 10}) {
    returning {
      id
      name
    }
  }
}
```

5. Head to the `GraphiQL` tab in the console and try running the following query:

```
query {
  profile {
    id
    name
  }
}
```

6. You’ll see that you get all the inserted data!
   ![alt text](https://docs.hasura.io/1.0/_images/profile-query1.png 'query data')
