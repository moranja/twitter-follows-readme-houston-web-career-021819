# Twitter Follows

## Objectives

1. Create a complex Domain Model
2. Implement an active follow relationship (following )
3. Implement the passive relationship (i.e. followers )  

## Instructions

In Twitter, a user follows many other users. That person can be followed by many people. For example, I follow @coffeedad and @cher. @coffeedad has many followers and so does @cher.

Take a few minutes and discuss this with your tablemates. How you would you domain model this out? What tables/foreign keys would you need? Once you've sketched out an ideal, check out the chapter below from the Rails tutorial to see one way you might do it.

This is a many-to-many relationship with itself.

Users - < Connections > - Users

class Users
has_many :connections
has_many :followers, through: :connections
has_many :followees, through: :connections
...

class Connections
belongs_to :follower, class_name: "User"
belongs_to :followee, class_name: "User"
...

Connections table would have a foreign key for follower, and for followee.

## Resources

* [Rails Tutorial - Following Users](https://www.railstutorial.org/book/following_users)

<a href='https://learn.co/lessons/twitter-follows' data-visibility='hidden'>View this lesson on Learn.co</a>
