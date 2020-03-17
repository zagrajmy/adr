# Get rid of Django

## Status

proposed

## Context

When we started work on Zagrajmy we made certain
assumptions about our backend and database
and decided to use Django because:
* Django models will be source of truth about db
* We'll use Django migrations instead of Hasura
* We'll need REST API for some endpoints
  connected to authentication and users

However, using Django has also some drawbacks
we couldn't foresee:
* Django models are not 1-1 representable in db,
  especially the DEFAULT values of fields, which
  makes us either write lots of SQL migrations
  or use hasura migrations instead. The latter
  means we won't be able to use Django migrations
  and models no more.
* Hasura migrations are better for frontend,
  because adding default values or changing db
  schema won't require changes in Django code.
* Finally, the default user model provided by
  Django is too much integrated into the framework
  and can't be changed to suit our needs.
  We need to keep certain fields even if
  we won't use them.
  And as we are going to use third-party auth
  and can manage db from hasura admin panel
  we don't need most of these fields.

## Decision

I suggest to get rid of Django and instead
go for small microservices that will execute
actions triggered by Hasura hooks. Most of
business logic is now in the frontend code.

## Consequences

We've not made much on backend so far, but 
nevertheless we are going to delete working code
and start everything from scratch on backend
side.