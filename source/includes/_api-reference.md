
# API Reference


# Subscriptions
 The Subscribers endpoint allows subscriber to register their node to receive blockchain events from the Encoded Listener.

## Create a Subscription

  ```shell
    curl -X POST 'http://localhost:8080/subscriptions'
  ```

  ```javascript
    const request = require('request');
    request(
        'http://localhost:8080/subscriptions/', 
        { json: true }, 
        (err, res, body) => {
          console.log(body.explanation);
        }
    );
  ```

  The request to create a new Subscription.

### Parameters

  Parameter        | Type    | Description 
  ---------------- | ------- | ----------- 
  callbackUrl      | string  | Target target URL to POST Encoded Listener events to.
  minConfirmations | integer | Confirmations required before event is sent to subscriber.

### HTTP Request
  `POST http://localhost:8080/subscriptions`

## Get a Subscription

  ```shell
    curl -X GET 'http://localhost/subscriptions/{id}'
  ```

  Get a Subscription by identifier.

### Parameters

  Parameter       | In   | Type    | Required | Description             
  --------------- | ---- | ------- | -------- | ----------------------- 
  name            | path | string  | True     | Subscription identifier

### HTTP Request
  `GET http://localhost:8080/subscriptions/{id}`


















# Event

## List Subscription Events

  ```shell
  curl -X GET 'http://localhost:8080/subscriptions/{id}/events'
  ```

  ```javascript
  const request = require('request');
  request(
      'http://localhost:8080/subscriptions/' + subscriptionId + '/events', 
      { json: true }, 
      (err, res, body) => {
        console.log(body.explanation);
      }
  );
  ```

  Gets a page of Subscription Events.

### Parameters

  Parameter       | In    | Type    | Required | Default | Description             
  --------------- | ----  | ------- | ----     | ----    | ----------------------- 
  name            | path  | string  | True     |         | Subscription identifier 
  pageSize        | query | integer |          | 100     | Number of items to return per page. 
  page            | query | integer |          |         | Zero-offset page number to return.
  continuation    | query | string  |          |         | Continuation param for fetching next page.

### HTTP Request
  `GET http://localhost:8080/subscriptions/{id}/events`














# Unsubscribe

## Create an Unsubscribe

  ```shell
  curl -X POST 'http://localhost:8080/subscriptions/{id}/unsubscribes'
  ```

  ```javascript
  const request = require('request');
  request(
      'http://localhost:8080/subscriptions/' + subscriptionId + '/unsubscribes', 
      { json: true }, 
      (err, res, body) => {
        console.log(body.explanation);
      }
  );
  ```

  Unsubscribes an active Subscription.

  > Returned response:

  ```json
  {
    "id": "329857298735983",
    "created_at": "2017-11-08T05:34:54.267Z"
  }
  ```

### Parameters

  Parameter       | In    | Type    | Required | Description             
  --------------- | ----  | ------- | ----     | ----------------------- 
  id              | path  | string  | True     | Subscription Identifier

### HTTP Request
  `POST http://localhost:8080/subscriptions/{id}/unsubscribes`








# Health

## Get Health of node.

  ```shell
    curl -X GET 'http://localhost:8080/status'
  ```
  Get application health information.

### HTTP Request
  `GET http://localhost:8080/status`


