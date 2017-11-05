# Laravel GraphQL

Here is demo application that implements GraphQL API.
Application based on Laravel.

<!--- See [**demo**][1] for more details -->

# Installation

1 . Clone repository

```
git clone https://github.com/antonshell/laravel-graphql.git
```

2 . Install dependencies

```
composer install
```

3 . Create database from data.sql dump

4 . Edit .env file. Set database name anm mysql login/password

# Examples

1 . Fetch users

```
/graphql/custom?query=query+FetchUsers{users{id,email}}
```

response:

```
{"data":{"users":[{"id":"1","email":"ivarnes0@nasa.gov"},{"id":"2","email":"gcreenan1@army.mil"},{"id":"3","email":"apedden2@boston.com"},{"id":"4","email":"epenswick3@discovery.com"},{"id":"5","email":"mduro4@statcounter.com"},{"id":"6","email":"cpetrushka5@zimbio.com"},{"id":"7","email":"jbeach6@mit.edu"},{"id":"8","email":"hpiddletown7@histats.com"},{"id":"9","email":"wperin8@digg.com"},{"id":"10","email":"vpumphrey9@tumblr.com"}]}}
```

2 . Fetch single user

```
/graphql?query=query+FetchUsers{users(id:"1")+{id,email}}
```

response

```
{"data":{"users":[{"id":"1","email":"ivarnes0@nasa.gov"}]}}
```

3 . Update user password(mutation)

```
http://127.0.0.39/graphql?query=mutation+users{updateUserPassword(id:%20%221%22,%20password:%20%22newpassword%22){id,email}}
```

response

```
{"data":{"updateUserPassword":{"id":"1","email":"ivarnes0@nasa.gov"}}}
```

[1]: http://demo.antonshell.me/laravel-graphql