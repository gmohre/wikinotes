# Identity
## Key Features

+ Mid : What are the differences between a visitor and a staff user. Permission groups. Connecting a Person to your user.
    + Hi: What does being a logged in User allow you to do? What does it enable in our system?

+ Lo: User model, different tracking methods, apis available.

### Product

1. How can I log in ? 
2. How can I register? 
3. How can I change my user properties?
4. How do I log out?
5. Why would I want to log in?
    1. Comments
    2. Crowdsourcing
    3. Discover
    4. Cms Census?
    5. Pledge Free Stream
    6. Email This (Proto Social Sharing :3)
    

### Staff
1. The Admin Site
2. Connecting your user to a Person object
3. User permissions
    1. Application Access
    2. Special View Permissions
4. Changing Password
5. Overriding Username in Comments

### Developers

#### Kennel
1. User Model
2. Apis to get user state
3. User action tracking (listen/view)
4. Comment and Person FKskennel
5. Logged In Users - Kennel application
	+ Registration
	+ Authentication
	+ Profile
	    - Avatar
	    - Display Name 
	    - Email
	    - Password
		- Communication Preferences
	+ Tracking of View/Listen Events
	+ Recommendation
	   - API
    	   + Listen Actions
    + Oemed
        - User Perms Verification
    + NPR
        - Special NPR user to associate with NPRArticles
        - Breaking News message to User 
	+ Crowdsourcing
	+ Comment Username Persistance
	+ Signals on User created
	+ Login Rate Limiting
	+ Etag
	+ Force Password Refresh for Staff Users
	+ Pledge Goal
	+ Overrides Admin Redirect View django.contrib.redirects.models.Redirect
	
6. Anonymous Users
	1. Uses browser_id for tracking
	2. Requires Email and Name for commenting
	3. Location Optional
7. Pledge Sync

## Missing
1. User Equivalence
## Missing Notes
1. How does ember utilize the user?
2. Architecture : What are the customizations in registration urls?
	1. Would prefer a visual of the model
	2. Does not provide insight on the relations between a User and a Person, which are used for appearances in stories.
2. Dev Guide - There is so little here, I don't know where to start 

# CMS

### Product
+ What is the Puppy Project?
    + CMS
        - Stories
        - Channels
        - RSS
    + Touts
        - Bucketslots
        - Buckets
        - Touts
    + Crowdsourcing
    + Comments
    + NPR Ingest
    + Images
    + Audio Processing
### Staff
### Developers
## Key Concepts
Hi: What are these containers, how do they relate to on air content, what flexibility do they provide our admin users?
Mid : Describe admin functionality
Lo: Describe models, apis, view structure, request stack.
1. Story
    1. Article
    2. Episode
    3. Segment

2. Channels
    1. Show
    2. ArticleChannel
    3. Series
3. Touts
    1. Bucket
    2. BucketItem
    3. Tout
4. Feeds
    1. Feed Types
    2. Feed Params
    3. Feedburner

## Criticisms of Docs:
1. Too Many Compacted Messages due to lack of audience scope (developer/admin user/layperson)
##Trash
1. Dashboard
2. Blogadmin
3. Homepage Preview
4. Why is there TaggingAdmin in Kennel? 
5. Hub?