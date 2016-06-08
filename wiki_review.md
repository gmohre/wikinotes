# Identity
## Key Features

+ Mid : What are the differences between a visitor and a staff user. Permission groups. Connecting a Person to your user.
+ Hi: What does being a logged in User allow you to do? What does it enable in our system?

+ Lo: User model, different tracking methods, apis available.

### Product
1. Why would I want to log in?
    Hello, feel welcome to explore WNYC.org
    1. Comments
        - For logged-in users, we pre-populate the required comment fields, allowing for a seamless route to interacting with our content.
        - To facilitate continued conversations we aggregate all of your comments on your user profile page.
        - [[comments gif]]
    2. Crowdsourcing
        - Some of our Crowdsourcing Surveys require a user to log in, to prevent distorted results.
        - [[sweet map interaction gif]]
    3. Discover
        - Track Listen Actions
            + By logging in, your interactions with our audio content is tracked, and we utilize this data to help you Discover new content.
        - [[sweet discover gif]]
    4. Pledge Free Stream
        - pledge free language
    5. Email This (Proto Social Sharing :3)    
        - discuss social features on a larger scale?
2. How can I log in ? 
    - In our header, we provide links for login and once logged-in, a users profile page.
    - [[sweet login button animation]]
3. How can I register? 
    - We provide a link to the registration form at our login page, requiring three fields:
        + Display Name
        + Email Address
        + Password
    - The registration form presents an opportunity to connect a User with our newsletter through an opt-in checkbox. 
    - [[sweet registration animation]]
4. How can I change my user properties?
    - Clicking on your username in the upper right hand corner of WNYC.org will send you to your profile page, where you can updated your profile
5. How do I log out?
    - As a logged in User, the login button is replaced with a logout button.

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
    - [django.contrib.auth.User](https://docs.djangoproject.com/es/1.9/ref/contrib/auth/)
    - FK references
        + ManagedItem.creator ('created_items')
        + MangedItem.last_editor ('edited_items')
        + Comment and Person FKskennel
        + [Visual](http://visualofmodel.png)   
2. API
    - [User Logged-In State](https://wiki2.wnyc.org/index.php?title=Identity:API_Reference)
    - [User Action Tracking](https://wiki2.wnyc.org/index.php?title=Identity:API_Reference#Tracking)
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
    + Oembed
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
	+ Decorators
	   - user_passes_test decorator to control per-view access
	   - puppysite/puppy/util/basicauth.py 
	   - puppy/cms/views/shows.py:upcoming - Manager is selected on request.user.is_staff
	+ CMS Admin
	   - Many CMS Admin classes utilize request.user and user groups to control flow / attribution (creator/last_editor)in ManagedItem FKs
	+ Middleware
	   - EnvironUserMiddleware sets request.environ['django_username key'] to request.user.username if user && user.is_authenticated
	  
	+ Jobs
	   - scripts/compute_email_hash_for_existing_users.py  
	       + Updates UserData for all users
	   - scripts/ffsupdate.py
	   - scripts/report_weekly_data.py
	   - scripts/remove_unusable_sessions.py 
	   - scripts/import_archives.py 
	   - scripts/user_email_migration.py 

+ DummyUser
    - puppy/util/djview.py 



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
6. Profile Middleware
7. Cms Census?
