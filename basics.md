# Curl basics

curl [options] [URL...]

- -X, --request - The HTTP method to be used.
- -i, --include - Include the response headers.
- -d, --data - The data to be sent.
- -H, --header - Additional header to be sent.

**GET

>curl -X GET https://hriday.org/blog?id=13

POST

>curl -X POST -d "id=13&title=Protest&body=Protests in a lot of cities." https://hriday.org/blog

For JSON data,

>curl -X POST -H "Content-Type: application/json" -d '{"id": 13, "title": "Protest", "body": "Protests in a lot of cities."}' https://hriday.org/blog

**PUT

>curl -X PUT -d "id=13&tag=BLM" https://hriday.org/blog/13

**PATCH

Same as above. Typically, PATCH is used for smaller PUT operations. 

**DELETE

>curl -X DELETE https://hriday.org/blog/13

**AUTHENTICATION

>curl -X GET -H "Authorization: Bearer {ACCESS_TOKEN}" https://hriday.org/blog?id=13

Other methods include

>curl -d '{"auth":{"passwordCredentials":{"username": "blogwriter","password": "XXXXX"},"tenantName": "HRIDAY"}}' -H "Content-Type: application/json" https://hriday.org/blog?id=13

You can put the json part in a file, say creds.json, and call

>curl -d @creds.json -H "Content-Type: application/json" https://hriday.org/blog?id=13

More curl options

- --insecure - Ignore HTTPS certificate.
- -c - Store the data erceived into a cookie file.
- -b - Reuse the cookie data in a subsequent command.

> curl --insecure -c cookies.txt -X POST -d 'username=admin&password;=admin' https://hriday.org/login

> curl --insecure -b cookies.txt -d @creds.json -H "Content-Type: application/json" -X POST https://hriday.org/login


