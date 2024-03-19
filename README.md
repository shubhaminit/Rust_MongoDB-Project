# Rust_MongoDB Project

An application that uses MongoDB with Rust.

The functions of the main files are:-
1. The `db.rs` file performs the majority of logic for the database.
2. The `error.rs` file handles all the errors of rejection or 404(not found).
3. The `handler.rs` file forwards requests to the database.

## Run
```bash
make mongostart

make dev
```

Runs a local mongodb instance using Docker and an HTTP server on http://localhost:8080.

You can then use CRUD operations on the book resource like this:

Fetch all books:

```bash
curl http://localhost:8080/book
```

Create a new book:

```bash
curl -X POST http://localhost:8080/book -d '{"name": "Demon Slayer", "author": "Koyoharu Gotouge", "num_pages": 480, "tags": ["fiction", "manga"]}' -H "content-type: application/json"
```

Edit a book:

```bash
curl -X PUT http://localhost:8080/book/5f15fd5400b98edc001944c0 -d '{"name": "Demon Slayer", "author": "Koyoharu Gotouge", "num_pages": 650, "tags": ["fiction", "manga"]}' -H "content-type: application/json"
```

Delete a new book:

```bash
curl -X DELETE http://localhost:8080/book/5f15fd3900789205001944bf
```
