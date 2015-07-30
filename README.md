# aws-sign-v4
A library for AWS Signature version 4.

## Install
```
npm install --save aws-signer-v4
```

## Usage
```js
// Prepare your request information
var request = {
  body: '',
  headers: {
    Date: new Date().toISOString(),
    Host: 'apigateway.us-east-1.amazonaws.com'
  },
  method: 'GET',
  url: 'https://apigateway.us-east-1.amazonaws.com/restapis'
};

// Create a Sign instance
var Sign = require('aws-sign-v4')
var sign = new Sign(
  accessKeyId: 'AWS_ACCESS_KEY_ID',
  body: request.body,
  headers: request.headers,
  method: 'GET',
  region: 'ua-east-1',
  secretAccessKey: 'AWS_SECRET_ACCESS_KEY',
  url: request.url
);

// Call #toString method to generate Authorization header value
headers.Authroziation = sign.toString()
```
