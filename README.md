# Just Tech News 📰

## Purpose
The back end of a Hacker News clone. Interact with the database at the heroku deployment. Make a user profile, create posts, write comments, and more!

## Deployment
Use this route when making requests: https://safe-fjord-78314.herokuapp.com/

## Routes 📍
### GET
Get requests can be made for users, comments, and posts. To make a get request, simply append the type of data you would like to retrieve.   
Example request to GET all users: ```https://safe-fjord-78314.herokuapp.com/api/users```   

Optionally, you can suppply an id to the end to get one specificed user or post.  
Example request to GET a user with an id of 1: ```https://safe-fjord-78314.herokuapp.com/api/users/1```

### DELETE
Similarly, users, posts, and comments can be deleted. Make a request to the url and append it with the type of data you are deleting along with the piece of data's id.  
Example request to DELETE a user with an id of 1: ```https://safe-fjord-78314.herokuapp.com/api/users/1```

### POST
Create new data with a post request. Make a request to the url and append it with the type of data you would like to create (new user, post, or comment). In the request body, supply the necessary information. Please follow the schema below:

#### New user
```
{
    "username": "<username>",
    "email": "<user email>",
    "password": "<user password>"
}
```

#### New Post
```
{
    "title": "<post text>",
    "post_url": "<post url>",
    "user_id": "<id of user who posted>"
}
```

#### New Comment
```
{
    "comment_text": "<comment text>",
    "user_id": "<id of user who commented>",
    "post_id": "<id of post to be commented on>"
}
```
##### A note about password security
Passwords are hashed with bcrypt. Password hashes are also not shown when getting user data.

### PUT
Users can upvote posts by making a put request. Send a request at the url and append "/api/posts/upvote" as well as sending a request body.  
Example upvote put request: ```http://localhost:3001/api/posts/upvote```

#### Example PUT request body
```
{
    "user_id": <id of user upvoting>,
    "post_id": <id of post to upvote>
}
```

## Built With
* Javascript
* Node
* Heroku
* Express
* Sequalize
* MySql
* MySql2
* Bcrypt

## Contribution
Made with ❤️ by Jonathan McDonnell
