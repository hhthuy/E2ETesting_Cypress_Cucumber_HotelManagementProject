# E2ETesting_Cypress_Cucumber_HotelManagementProject
> E2E Testing using Cypress and Cucumber for Hotel Management Project

## Test suite

### M01_BUI_Login
- Login With Email, Password, Reservation Code, Social Network Account
- Register a new account
- Forgot password
- Change Password
- Update personal information

### M02_BUI_Booking 
- Search room
- Room reservation
- Enter special requirements when booking 
- Choose additional options when booking
- Choose flexible payment methods 
- Payment
- Booking confirmation
- Cancel reservation
- View booking details
- Modify booking
- View booking history
- Contact customer support

### M03_BUI_Promotion
- View offers, discount codes, vouchers, rewards points, membership programs, refund policies
- Subscribe to receive news
- Refer friends

### M04_BUI_Information
- View  the hotel or location
- View  amenities/services
- View  policy/ safety
- View comments, reviews, FAQs

### M05_BUI_Option
- Change language
- Currency change
- Contact the hotel

### M06_BUI_Payment
- Select a payment method
- Enter credit card information
- Login to your PayPal account
- Confirm payment
- Cancellation of payment
- Payment refund
- View the bill
- Download receipts

### M07_BUI_Search
- Enter keywords
- Filter results by price, rating, amenities, distance
- Sort results by default, ascending, descending
- View room details for search
- Compare rooms

### M08_BUI_Help
- Chat with chatbots
- Chat with support staff
- Call the hotel
- Email the hotel
- Send feedback to the hotel

### M09_BUI_Feedback
- View customer reviews about hotels, rooms, services, booking, payment, cancellation, room repair
- View the average score
- View  the number of reviews
- Reviews hotel, room, service, booking, payment, cancellation, room repair
- Edit/delete review and feedback
- Reply to other users
- Report inappropriate feedback

### M10_BUI_Comparison
- Select two or more rooms to compare
- View information about prices, amenities, services, policies
- Rate the selected rooms
- View the differences and similarities of selected rooms
- Reservation for priority room

### M11_BUI_Newsletter
- Enter your email to subscribe to news, offers, promotions, announcements from the hotel
- Confirm your email
- Unsubscribe from newsletters
- Change the frequency of receiving messages
- View Sent Messages

### M12_BUI_Referrals
- Enter your email and the email of your friends to recommend the hotel to them
- Confirm your email and friends
- Get a discount code or bonus points when your friends make a successful booking
- View friend referral history

### M13_BUI_Membership
- Register as a member of the hotel
- Enter personal information, email, password
- Confirm information
- Log in to your member account
- View member benefits, incentives, bonus points
- Convert reward points into vouchers or discounts
- Update personal information

### M14_MUI_Room House Keeping
- The Room List Management
- Room Status Management
- Cleaning Service Management
- Management of special requests
- Room Facilities Management

### M15_MUI_Room Management
- Add new room
- Edit room information
- Delete room
- Search room
- View room detals

### M16_MUI_Employee Management
- Add new employee
- Edit employee  information
- Delete employee
- Search employee
- View employee details

### M17_MUI_Statistics & Reports
- View reservation, usage, payment and report data
- Filter 
- Sort 
- Export report

### M18_MUI_Locking Service
- Lock room
- Unlock room
- Create room key code
- Send room key code
- View room lock history

### M19_MUI_Membership & Rates
- Manage room rates
- Manage membership

## Test case
### Feature: Login 
#### Test Suite: Login With Email, Password, Reservation Code, Social Network Account
- Happy case
    - Valid login with email and password and access booking page 
        - Email
            - Enter Valid Email 
            - Enter Invalid Email Format - no @ character
            - Enter Invalid Email Format - no domain name
            - Enter Invalid Email Format - no username 
            - Enter Invalid Email - Non-existing User
        - Password
            - Enter Valid Password
            - Enter Invalid Password - Length Less than 8 Characters
            - Enter Invalid Password - No Letter
            - Enter Invalid Password - No Number
            - Enter Invalid Password - No Letter and No Number
    - Valid login with reservation code and view booking details
    - Valid login with social network account and access booking page 
    - Click the Sign in button and view their bookings with valid email and password
    - Logout from the account and verify the homepage and login option are displayed.
    - Reset their password or retrieve the reservation code from the login page and and receive an email with a link or code to proceed.
    - Create a new account from the login page and receive a confirmation email with an activation link.
- Unhappy case
    - Invalid credentials and receive an error message with password reset 
        - Enter Invalid email and invalid password
        - Enter Valid email and invalid password
        - Enter Invalid email and valid password
        - Enter Empty email and empty password (Edge cases)
        - Enter Empty email and valid password (Edge cases)
        - Enter Valid email and empty password (Edge cases)
        - Enter Email and Password contain special characters (abnormal)
        - Enter Email and Password with more than maximum length (abnormal)
    - Wrong email and password 3 times
    - Leave the email and password field blank
    - View an error message when entering an invalid and blank email or password

#### Test Suite: Register a new account
- Happy case
    - Register from the login page or homepage.
    - Register with valid credentials and receive a confirmation email.
    - Register using a valid social network account and receive a confirmation email.
    - Activate the account using the link in the confirmation email.
- Unhappy case:
    - Register with invalid credentials and receive an error message.
    - Register with an existing email or social network account and receive an error message.
    - Activate the account with an expired or invalid link and receive an error message.

#### Test Suite: Forgot password
- Happy case
    - Access the "Forgot password?" option from the login page.
    - Enter a valid email address and receive an email with a link or code to reset their password.
    - Reset their password by clicking on the link or entering the code in the email and providing a valid new password.
- Unhappy case
    - Reset their password with an invalid or mismatched new password and confirm password.
    - Reset their password with an expired or invalid link or code.

#### Test Suite: Change Password
- Happy case
    - Valid current password
    - Valid new password
    - Valid confirmation of new password
- Unhappy case
    - Cannot change password with invalid or incorrect current password
    - Cannot change password with new password that is the same as current password
    - Cannot change password with a social network account

#### Test Suite: Update personal information
- Happy case
    - Access the update personal information option from their profile page.
    - Update their personal information with valid inputs and see a success message.
- Unhappy case
    - Cannot update their personal information with invalid or incorrect inputs and get an error message.
    - Cannot update their email with an existing email and get an error message.
    - Cannot update their personal information with a social network account and get an error message.

### Feature: Booking 
#### Test Suite: Search room
- Search hotels by destination by a dropdown with
    - valid selection locations
    - invalid selection locations
    - partial or incomplete selection locations
    - no selection
    - multiple selections
- Search room by check-in and check-out dates
    - valid check-in and check-out dates
        - Check-in date must be before check-out date.
        - Check-in and check-out dates must be in the future.
        - Check-out date cannot be more than one year from the check-in date.
    - invalid check-in and check-out dates
        - Check-in date is after check-out date.
        - Check-in or check-out date is in the past.
        - Check-in and check-out dates are more than one year apart.
        - Check-in date is the same as check-out date.
    - Invalid Date Format
    - Without selecting check-in and check-out dates
    - Cannot be selected if all rooms are fully booked
    - Selecting dates along with other filters(e.g., number of guests, destination, etc.).
    - Selected dates must be valid for the selected room type(e.g. standard, family...)
    - Selected dates may not be eligible for special offers or discount
    - Additional Restrictions
        - Check-in date within the next 24 hours
        - An extended stay (more than 30 days)
        - Check-in date that falls on a public holiday
- Search the number of adults and children for the booking
    - without selecting the number of adults and children
    - valid values
    - invalid values
        - more than 4 adults 
        - more than 4 children
        - less than 1 adult
        - less than 0 child
    - zero values
    - empty
    - a higher number of children than adults
- search rooms by valid location, check-in date, check-out date and number of guests 
- search rooms by invalid destination, check-in and check-out dates, or number of guests
- search rooms by partial or incomplete destination, check-in and check-out dates, or number of guests
- view the price and availability of rooms after searching
- filters to narrow down the search results (e.g., by price, rating, or distance).
- sort the search results by price, rating, and distance


#### Test Suite: Room reservation
- Happy case: Can book a room with
    - Without entering the city, check-in date, check-out date or number of guests
    - invalid city, check-in date, check-out date or number of guests
    - check-in date after check-out date
    - number of guests exceeding the room capacity
    - that is out of stock
    - without entering your personal information, email or phone number
    - invalid personal information, email or phone number
    - without choosing a payment method
    - invalid credit card information or PayPal account
    - special requests or preferences
    - accessibility features or services
    - extra amenities or facilities
    - a flexible cancellation policy
    - a loyalty program or a membership benefit
    - a best price guarantee or a price match
    - a customer review or a rating
    - a gift card or a credit voucher
    - a group booking or a corporate booking
    - a travel insurance or a cancellation protection
    - a pet-friendly policy or a family-friendly policy
    - a breakfast option or a meal plan
    - a late check-in or a late check-out
    - a free Wi-Fi or a free parking
    - a spa service or a fitness center
    - a concierge service or a luggage storage
    - a online check-in or a self-service check-in
    - a social media login or a guest login
    - a newsletter subscription or a promotional offer
    - a referral code or a reward point
    - a feedback survey or a satisfaction rating
    - a chatbot support or a live chat support
    - a COVID-19 safety measure or a hygiene standard
    - a environmental policy or a sustainability initiative
    - a local attraction or a tour package
    - a airport shuttle or a taxi service
    - a invoice request or a receipt download
    - Can cancel your booking and get a refund
    - Can modify your booking and update your information
    - Can view your booking history
    - Can contact the hotel's customer support if you have any issues with your booking
    - Can book multiple rooms in one booking
    - Can apply a discount code or a voucher to your booking
    - Can change the currency or the language of the website
- Unhappy case: Cannot book a room when
    - The website is down or under maintenance
    - The payment gateway is not working or not secure
    - The booking confirmation email is not sent or not received
    - The booking code is not generated or not valid
    - The booking details are not saved or not updated
    - The booking cancellation email is not sent or not received
    - The booking refund is not processed or not credited
    - The booking modification email is not sent or not received
    - The booking change is not reflected or not confirmed
    - The customer support is not available or not responsive
    - The website is slow or unresponsive
    - The payment method is not supported or not accepted
    - The booking information is not correct or not complete
    - The booking limit is reached or exceeded
    - The booking policy is not clear or not fair
    - The booking fee is not transparent or not reasonable
    - The booking date is not available or not flexible
    - The booking location is not convenient or not accessible
    - The booking quality is not guaranteed or not satisfactory
    - The booking service is not friendly or not helpful
    - The website is hacked or compromised
    - The payment information is stolen or misused
    - The booking confirmation is fake or fraudulent
    - The booking code is duplicated or expired
    - The booking details are leaked or altered
    - The booking cancellation is denied or delayed
    - The booking refund is partial or conditional
    - The booking modification is restricted or charged
    - the booking change is rejected or ignored
    - The customer support is rude or unprofessional

#### Test Suite: Payment
- Happy case
    - valid payment information
    - valid credit card
    - valid debit card
    - PayPal
    - valid discount or promo code and get the reduced price.
    - different currencies
- Unhappy case
    - Invalid credit card number
        - Incorrect CVV number
        - Invalid expiration date
    - Expired credit card
    - Unsupported payment method
    - Insufficient funds in the credit card
    - Invalid or expired discount code
    - Payment foreign currency not supported
    - Network issues
    - Payment timeout
    - Payment declined by the bank
    - Cannot cancel the booking and get a refund after

#### Test Suite: Booking confirmation
- View booking details
- Download booking confirmation as a PDF
- Print booking confirmation
- Send booking confirmation via email
- Modify booking details
- Cancel booking
- Contact customer service via phone, email, or chat are available.
- View policies
- Rate booking experience and provide feedback

#### Test Suite: Cancel reservation
- Cancel reservation and receive confirmation and refund details
- Cancel reservation within the cancellation policy
- Cannot cancel reservation after the cancellation deadline
- Cancel reservation with a discount code and receives a refund of the discounted price.
- Cancel reservation with PayPal and receives a refund to their PayPal account.
- Cancel multiple reservations at once
- View cancellation history and details

#### Test Suite: View booking details
- View booking details from the confirmation page or email link
- View booking details for multiple reservations
- View booking details for different hotels and locations
- View  booking details for different dates
- View booking details for different numbers of guests
- View booking details with a discount code
- View booking details with PayPal
#### Test Suite: Modify booking

#### Test Suite: View booking history

#### Test Suite: Contact customer support
- Access the customer support from the homepage, the email link
- Contact the customer support by phone 
- Contact the customer support by email 
- Contact the customer support by chat 
- Contact the customer support for different reasons
- Contact the customer support for different languages

### Feature: MUI_Room Management

#### Test Suite: Add new room
#### Test Suite: Edit room information
#### Test Suite: Delete room
#### Test Suite: Search room
#### Test Suite: View room detals


