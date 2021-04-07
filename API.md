# Getting started

To get your authorization token, go to your bot edit page, and use the authorization tab. You can post server count 
and get users that have liked a specific bot. Pass this authorization token in a header. Both of these requests will 
be RateLimited.

# Sending requests

| API Endpoint              | Method | Function                                                              |
| :------------------------ | :----: | :-------------------------------------------------------------------- |
| `/api/auth/liked/:botid`  | GET    | Get a list of users that have liked this bot within the last 12 hours |
| `/api/auth/stats/:botid`  | POST   | Post server count                                                     |

<sub>(Make sure you include the domain in the url)</sub>

The API allows for hypertext transfer protocol GET Methods to be placed.

This allows users to get bot data from asynchronous scripts.

Here are some language specific examples:

## NodeJS
```js
var requestOptions = {
  method: 'GET/POST', // Choose the appropriate method
  headers: {
    "authorization": "YOUR_AUTH_TOKEN",
    "Content-Type": "application/json"
  },
  body: JSON.stringify({"server_count": 1500}) // Replace this number with the server count
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

To download Data, Run

```bash
wget https://api/auth/[mod]/:botid
```

The examples above get a certain JSON string from the website.
To get certain return values of bot data, Use the URL in a 
hypertext transfer protocol **GET** method, after the URL.

`api/auth/[mod]/:botid`

Where `[mod]`=Your Bot's Statistic.

You can use Bot Statistic Integers using the `parseInt()` JS Method,
The `int()` method, and WGET For getting things that can be transferred.

