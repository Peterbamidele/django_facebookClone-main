Requirements

Functional
Users can share, like, comment, update, delete post
Users can add and remove friends
Users can change post access to public/private
Users can see news feeds
Users can search for friends
Users can share profile
Users can delete account
Non-functional
Application should be secure -Application should be available
Database Design
-POST - id: bigInt, auto-increment, primary - text: text - author: USER - created_on: datetime - updated_on: datetime

-POST-MEDIA - id: bigInt - file: varchar(url) - post: POST - created_on: datetime - updated_on: datetime

-USER - id: bigInt, auto-increment, primary - username: varchar - email: varchar - created_on: datetime - updated_on: datetime

-PROFILE - id: bigInt, auto-increment, primary - owner: USER - image: varchar(url) - address: ADDRESS - created_on: datetime - updated_on: datetime

-LIKE -id: bigInt, auto-increment, primary -post: POST -owner: USER -created_on: datetime -updated_on: datetime

-COMMENT -id: bigInt, auto-increment, primary -text: text -author: USER -created_on: datetime -updated_on: datetime

-FRIEND -id: bigInt, auto-increment, primary -user: USER -friended: USER -created_on: datetime -updated_on: datetime

API Design
-[GET, POST, PUT, PATCH, DELETE] -[GET_LIST, GET_ONE, CREATE, UPDATE_ALL, UPDATE_SOME, DESTROY] -POSTS, USERS, COMMENTS, LIKES, FRIENDS

-POST -GET_LIST: returns a list of posts -URL: /api/v1/posts -METHOD: GET -REQUEST -HEADERS: Authorization -BODY:

    RESPONSE:
        -HEADERS: Authorization
        -BODY: {
            id: int,
            text: str,
            created-on: datetime,
            author: user
        }