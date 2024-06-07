# test-data-generator
Uses WireMock to generate test data via REST endpoints


# Execution Steps:

* In Terminal, Run command:
  
`docker compose up`

* Verify WireMock container service started successfully

* Monitor container, if required:
  
`docker ps`

* Use REST Client Tool like Postman and send request:

* To get list of all portfolios:

`GET http://localhost:8082/api/v1/portfolios`

Should return 200 OK with JSON response having ABC and DEF portfolios

* To get specific portfolio:

`GET http://localhost:8082/api/v1/portfolios/2df8c85a-9d8a-45ce-b929-827c92955e95`

Should return 200 OK with JSON response for ABC portfolio only

`GET http://localhost:8082/api/v1/portfolios/<invalid_uuid>`

Should return 404

# Adding New Test Data

* Clone this repo
* Go to *test-data/mappings* folder
* Make copy of existing json file and rename it with your domain
* Inside JSON, change *urlPathPattern* and add appropriate json response in *jsonBody*
* Run docker-compose and use Postman client to verify your new endpoint
