# Luminate Event Manager Center Scrapper
This project provides a basic API to execute updates in Luminate EMC, thus allowing in-line editing from a TeamRaiser Greeting page.

# TODO
- improve error handling, auth fails alot, need to get back proper error response and try auth again

- able to update event properties, should work on updating greeting page content

- currently always returing error even when we have success

## Getting Started

Install the necessary dependencies
```shell
yarn install
```

Then run the development server:
```bash
yarn start
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.


## API
All API endpoints are located in this application at */pages/api/* and each at a minimum take the following required params:
```javascript
params: {
  username, // Event Manager username
  password, // Event Manager password
  domain, // secure domain for client, eg https://fundraising.qa.stjude.org/
  frId // Event Id for the EMC that will be accessed
}
```

In addition each api method takes additional params as listed below.

### Event Properties
Updates to the Event Properties tab also take the following params:

```javascript
params: {
  targetField, // The field to update, this based of the inputs id attribute in the EMC
  content // string of string
}
```

Example endpoint would look like:
```
/api/event-properties?username=[username]&password=[password]&domain=https://fundraising.qa.stjude.org/site&frId=24014&targetField=shared_event_propsprop_sponsor_4.field&content=Oh%20boy%20this%20works

```
### Update Event Greeting Page Content

