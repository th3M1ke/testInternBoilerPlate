# Inter test

## Task to do

Create a simple http server, that checks logz.io region's application status(https://docs.logz.io/user-guide/accounts/account-region.html) every minute (in a background).

Http server should have one endpoint "/status" that return a JSON array of statuses with history of prev statuses:

```
[
  {
    domain: "app.logz.io",
    status: 200,
    timestamp: "2021-07-08T10:29:20Z"
    prevState: [
      {
         status: 200,
         timestamp: "2021-07-08T10:26:20Z"
      },
      {
         status: 200,
         timestamp: "2021-07-08T10:27:20Z"
      },
      {
         status: 200,
         timestamp: "2021-07-08T10:28:20Z"
      },
      ...
    ]
  },
  {
    domain: "app-nl.logz.io",
    status: 200,
    timestamp: "2021-07-08T10:29:20Z"
    prevState: [
      {
         status: 200,
         timestamp: "2021-07-08T10:26:20Z"
      },
      {
         status: 200,
         timestamp: "2021-07-08T10:27:20Z"
      },
      {
         status: 200,
         timestamp: "2021-07-08T10:28:20Z"
      },
      ...
    ]
  },
  ...
]
```

## How to run

1. `go build main.go`
2. `./main`
3. `curl localhost:putYourPortHere/status | json_pp`