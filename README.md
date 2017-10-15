# Giving
## Onboarding
Use Stripe connect to connect the user's Stripe account to Cornerstone.  **Do we need to store a token or credentials in the database for the user?**

##Setup
We will need something to seperate user's giving page.  This can be done with a subdomain (fcchurch.cornerstoneio.com) or using a slug (cornerstoneio.com/fcchurch)

Giving funds.  I would think we need to let the user setup different funds that donations goes towards.  **Would we want to use a default fund? (gifts that we dont know what they are for, it goes to that fund.  Do we need that?)**

##Cornerstone Administration
### View Contributions
* View all recent transactions buy time period
* View transactions by person
* View transactions by giving fund
* View Transactions by deposit date (more on that later)
* **How do we handle fees?**

### Stripe Administration
Refunded transactions should use a webhook to handle the Cornerstone side of things.
Canceling a recurring donation should use a webhook to mark gift as inactive

## Webhooks
* We need a webhook to set deposit information on a transaction as they are deposited into user's bank
* Webhook needed to create a contribution record in Cornerstone when recurring gift is fired.

## Giver's Portal
User logs in and has these pages:

* Page to view recent contributions made
* Page to view active and inactive recurring gifts, with the ability to cancel or edit a gift (I think we can edit a a gift)
* Page to create a new gift