# TwitterClone-Node-Js-A2

Twitter
Twitter
Given an app.js file and a database file twitterClone.db consisting of five tables user, follower, tweet, reply, and like.

Write APIs to perform operations on the tables user, follower, tweet, reply, and like containing the following columns,

User Table

Column	Type
user_id	INTEGER
name	TEXT
username	TEXT
password	TEXT
gender	TEXT
Follower Table

Column	Type
follower_id	INTEGER
follower_user_id	INTEGER
following_user_id	INTEGER
Here, if user1 follows user2 then,

follower_user_id is the user ID of user1 and following_user_id is the user ID of user2.

Tweet Table

Column	Type
tweet_id	INTEGER
tweet	TEXT
user_id	INTEGER
date_time	DATETIME
Reply Table

Column	Type
reply_id	INTEGER
tweet_id	INTEGER
reply	TEXT
user_id	INTEGER
date_time	DATETIME
Like Table

Column	Type
like_id	INTEGER
tweet_id	INTEGER
user_id	INTEGER
date_time	DATETIME
Sample Valid User Credentials
API 1
API 2
Authentication with JWT Token
API 3
API 4
API 5
API 6
API 7
API 8
API 9
API 10
API 11
API 1
Path: /register/
Method: POST
Request

Scenario 1

Description:

If the username already exists

Response
Status code
400
Body
User already exists

Scenario 2

Description:

If the registrant provides a password with less than 6 characters

Response
Status code
400
Body
Password is too short

Scenario 3

Description:

Successful registration of the registrant

Response

Status code

Body
User created successfully

API 2
Path: /login/
Method: POST
Request

Scenario 1

Description:

If the user doesn't have a Twitter account

Response
Status code
400
Body
Invalid user

Scenario 2

Description:

If the user provides an incorrect password

Response
Status code
400
Body
Invalid password

Scenario 3

Description:

Successful login of the user

Response

Return the JWT Token

Authentication with JWT Token
Write a middleware to authenticate the JWT token.

Scenario 1

Description:

If the JWT token is not provided by the user or an invalid JWT token is provided

Response
Status code
401
Body
Invalid JWT Token

Scenario 2
After successful verification of JWT token, proceed to next middleware or handler

API 3
Path: /user/tweets/feed/
Method: GET
Description:
Returns the latest tweets of people whom the user follows. Return 4 tweets at a time

Response
 
API 4
Path: /user/following/
Method: GET
Description:
Returns the list of all names of people whom the user follows

Response
API 5
Path: /user/followers/
Method: GET
Description:
Returns the list of all names of people who follows the user

Response
API 6
Path: /tweets/:tweetId/
Method: GET
Scenario 1

Description:

If the user requests a tweet other than the users he is following

Response
Status code
401
Body
Invalid Request

Scenario 2

Description:

If the user requests a tweet of the user he is following, return the tweet, likes count, replies count and date-time

Response
{
   "tweet": "T 3859 - do something wonderful, people may imitate it ..",
   "likes": 3,
   "replies": 1,
   "dateTime": "2021-04-07 14:50:19"
}

API 7
Path: /tweets/:tweetId/likes/
Method: GET
Scenario 1

Description:

If the user requests a tweet other than the users he is following

Response
Status code
401
Body
Invalid Request

Scenario 2

Description:

If the user requests a tweet of a user he is following, return the list of usernames who liked the tweet

Response
{
   "likes": ["albert", ]
}

API 8
Path: /tweets/:tweetId/replies/
Method: GET
Scenario 1

Description:

If the user requests a tweet other than the users he is following

Response
Status code
401
Body
Invalid Request

Scenario 2

Description:

If the user requests a tweet of a user he is following, return the list of replies.

Response

API 9
Path: /user/tweets/
Method: GET
Description:
Returns a list of all tweets of the user

Response
API 10
Path: /user/tweets/
Method: POST
Description:
Create a tweet in the tweet table

Request
Response
API 11
Path: /tweets/:tweetId/
Method: DELETE
Scenario 1

Description:

If the user requests to delete a tweet of other users

Response
Status code
401
Body
Invalid Request

Scenario 2

Description:

If the user deletes his tweet

Response
Tweet Removed


Use npm install to install the packages.

Export the express instance using the default export syntax.

Use Common JS module syntax.
