# Infrastructure engineer homework

Below you will find instructions for infrastructure engineer homework.

Your objection is to build service, that will handle user requests in a scalable manner. 

## Instructions
1. Clone/fork/copy this repo
2. Develop two services that utilize prewritten service
3. Put everything into Docker containers
4. Setup CI
5. Setup CD

### Pre-written service
There is already a service written for you. You can request it on HEROKU_CELTRA_URL. This service should get called by one of your services. Service have one API, reachable on path `/api/upload`. You should call service using POST method.

### Your services
You should develop two different services. 

The first service should be a validator service. It should expose one POST route. A route should be available on `user/USER_ID/data`, where `USER_ID` should be valid UUID v4. Request body can have many fields, but it should have properties `accountId`, `data` and `timestamp` set. A valid body should look like:
```json
{
    "accountId": "85010c53-eafd-4ce2-93c0-5818b593c25b",
    "timestamp": 1540462747,
    "data": "random string that can be valid JSON too"
}
```
Limit a data size to 10kB. After service was validated, call next service.

The second service should call our service. It should call it and handle all possible cases. If something goes wrong, you should handle it accordingly. 

### Docker containers
Every service should have its own Docker container.

### Setup CI
CI should build images and run tests. We want to have information about our run as soon as possible, so try to split service CI into multiple stages.

### Setup CD
After CI has passed all tests, your CD should deploy service on the cloud provider.

## Technologies
You can use any technology you like, as long as it is a proper fit for the solution. After you are done, you should write a short explanation of technologies you used.
