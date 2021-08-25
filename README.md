# Klink Platform Public Issue Tracker

## Products
- Klink Frontend (FE)
- Klink Admin Frontend (AFE)
- Klink Backend (BE)

## Version
v0.5.0 (MVP Internal Alpha)

## Features implemented
### Resources
* Accomodation (per night) + Room (hourly)
* Stacks: Create one resource and duplicate it by using instances (have their own occupation + availability)

### Availability + occupation
* Per resource
* Min + Max duration per stay
* After booking time span (per resource): Auto-block after each booking (e.g. to clean) by weekday in hours/days 
* Pre booking time span (global): Min. duration in advance of the booking (e.g. booking of rooms has to be min. 15min before the actual booking)
* Stack availability: Every instance can have its own availability + occupation and we distribute evenly distribute incoming bookings between them
* Occupation booking slot: Set occupied when booked
* [Occupation manual slot: Set manually to be occupied --> BE only]
* [Availablity single slot --> BE only]
* [Availablity reoccurring slots: Define rules which are used to create available time slots (e.g. Mo-Fr from 8-12 and 14-18 but not on day X and in interval of 2 weeks ending on day Y)  --> BE only]

### Authentication
* Authenticate via JWT

### Access management (ACL)
* Level-based access rights (top down)
  * Customer (default) -> Book
  * Project manager -> Manage
  * Resource manager -> Manage
  * Organsation manager -> Manage
  * Admin -> Manage everything
* User- and group-based roles for specific visibility, pricing and booking/managing actions

### Booking
* Direct- or approval-based booking
* Free booking
* [Paid booking --> BE only]
* Tax rates
* Customer note
* Billing address
* Pricing
  * Gross
  * Group-based
  * Business
  * Cleaning fees
  * First and additional persons
* [Payment method --> BE only]
* [Billing --> not implemented yet (via Stripe)]

### Account
* Register
* Activate account e-mail
* Resend activate account email
* Request reset password
* Reset password session
* Update account
* Update password

### I18n
* Currently only DE except for BE which uses EN

### Mailing
* Full mail support by Mailgun

### Content
* [Images --> not implemented yet (via Strapi or self-hosted)]

## Hints
* If you add manage roles to a user, the user has to logout and login again to see changes in the UI (Backend always recieves live updates)
