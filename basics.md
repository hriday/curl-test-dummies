# Curl basics

curl [options] [URL...]

-X, --request - The HTTP method to be used.
-i, --include - Include the response headers.
-d, --data - The data to be sent.
-H, --header - Additional header to be sent.

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


