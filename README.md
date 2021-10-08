# DoggoPlaydate

## Project Overview

The purpose of this application is to create a way for dog owners to schedule playdates at dog parks with other dog owners.  Too often, there are no other dogs at the park and my dog is bored.

## Libraries & Frameworks

### Backend

 - Django
 - DjangoRestFramework

### Frontend

 - Vue.js
 - Boostrap
 - Axios

# User Stories

### Story
As a dog owner, I want to be able to schedule dog park visits when I know other dogs will be there so my dog will have other dogs to play with.

### Tasks
 - Create "meetup" objects in database to represent owners scheduling dog park visits at the same time

### Story
As a dog owner, I want to match my dog with other dogs who would be good fits, because some dogs have different personalities.

### Tasks
 - Allow users to describe their dogs' tempermants so they can find good playdate matches.


### Story
As an admin, I want to be able to give dog owners temporary suspensionss because they said they'd come to the dog park but they didn't!

#### Tasks
 - Allow dog owners to report a no-show.
 - Allow admins to investigate no-shows and temporarily suspend dog owners for not coming to the park like they said they would.

## Schema (Data Model)

### Dog Owners
 - extends BaseUser model (if you're extending the base user model, do that first, check out some info here: [https://github.com/PdxCodeGuild/class_lemur/blob/main/4%20Django/docs/07%20User%20Management.md#extending-the-user-model](https://github.com/PdxCodeGuild/class_lemur/blob/main/4%20Django/docs/07%20User%20Management.md#extending-the-user-model))
 - Name (string)
 - Phone Number (string)
 - Address (not public, for showing how far away other owners are)
 - Email Address (string)
 - Bio (string)
 - Suspended (boolean)

### Dogs
 - Name (string)
 - Breed (string)
 - Size (small, medium, large)
 - Owner (Foreign Key)
 - Temperament (choices)
 - Friends (many to many with other dogs)
 - Good Boy/Girl (boolean, default=True)

### Playdates
 - StartDateTime (datetime) when you plan to get to the park
 - EndDateTime (datetime) when you plan to leave the park
 - your dog (ForeignKey to dog)
 - other dogs (many to many relationship to other dogs coming) other dog owners RSVPing to the playdate
 - dog park (text field? link to google maps?)

## Schedule
### Week 1
 - &check; create models
 - ~~create serializers~~
 - create ListCreateAPIViews
 - create simple vue app in template to test api with axios calls

### Week 2
 - Work on CSS
 - create RetrieveUpdateDestroyAPIViews
 - create Vue components for dog park schedule cards

### Week 3
 - create admin (stretch goal)
 - work on CSS
 - work on cool Vue SPA (single page application) features

### Week 4
 - allow admins to suspend
 - get CSS really lookin really good
 - allow admins to ban, but just Mary because she always doesn't show up


## Features
### Must Haves
 - Make Account -- Dog owners need to be able to make accounts
 - Add dogs -- Dog owners need to be able to register their dogs

### Should Haves
 - Schedule playdate for dogs
 - Allow other owners to join playdate

### Can Haves
 - Create admin roles
 - Allow admins to enforce community guidelines

### Won't Haves
 - Models for dog parks
 - Permabans for Mary