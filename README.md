# Getting started

To get your authorisation token, go to your bot edit page, and use the authorisation tab. You can post server count and get users that have liked a specific bot. Pass this authorisation token in a header. Both of these requests will be ratelimited.

# Sending requests

| API Endpoint              | Method | Function                                                              |
| :------------------------ | :----: | :-------------------------------------------------------------------- |
| `/api/auth/liked/:botid`  | GET    | Get a list of users that have liked this bot within the last 12 hours |
| `/api/auth/stats/:botid`  | POST   | Post server count                                                     |

<sub>(Make sure you include the domain in the url)</sub>

Here are some language specific examples:

## NodeJS
```js
var requestOptions = {
  method: 'GET/POST', // Choose the appropriate method
  headers: {
    "authorization": "YOUR_AUTH_TOKEN",
    "Content-Type": "application/json"
  },
  body: JSON.stringify({"server_count": 1500}); // Replace this number with the server count
};

fetch(URL, requestOptions) // Check the table above for url
  .then(response => response.text())
  .then(console.log)
  .catch(console.error);
```
## Python
```py
payload = "{\"server_count\": 1500}" # Replace this number with the server count
headers = {
  'authorization': 'YOUR_AUTH_TOKEN',
  'Content-Type': 'application/json'
}

response = requests.request("GET/POST", URL, headers=headers, data = payload) # Check the table above for url and choose the appropriate method
print(response.text.encode('utf8'))
```

cURL
```bash
curl -H "Content-Type: application/json" \
     -H "Authorization: YOUR_AUTH_TOKEN" \
     -X GET/POST \
     -d "{\"server_count\": 1500}" \
      "URL"

# Check the table above for url and replace the number with the server count
# Also, choose the appropriate method
```
