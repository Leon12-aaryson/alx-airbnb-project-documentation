# Use Case Diagram - Airbnb Clone Backend

## Overview
This document describes the use case diagram for the Airbnb Clone backend system, illustrating the interactions between different actors and the system's core functionalities.

## Actors

### Primary Actors
1. **Guest** - Users who book properties
2. **Host** - Users who list and manage properties
3. **Admin** - System administrators who manage the platform

### Secondary Actors
1. **Payment Gateway** - External payment processing system
2. **Email Service** - External email service provider
3. **SMS Service** - External SMS service provider

## Use Cases by Actor

### Guest Use Cases
1. **Register Account**
   - Guest creates a new account with email verification
   - Includes profile setup and preferences

2. **Login/Logout**
   - Secure authentication using credentials
   - Session management

3. **Search Properties**
   - Advanced search with filters (location, price, dates, amenities)
   - View search results and property details

4. **View Property Details**
   - Access comprehensive property information
   - View photos, descriptions, reviews, and availability

5. **Create Booking**
   - Select dates and submit booking request
   - Provide guest information and special requests

6. **Manage Bookings**
   - View booking history and status
   - Modify or cancel bookings (subject to policies)

7. **Make Payment**
   - Process payment for confirmed bookings
   - Handle payment failures and retries

8. **Leave Review**
   - Rate and review completed stays
   - Provide feedback on property and host

9. **Communicate with Host**
   - Send and receive messages
   - Get booking-related information

10. **Manage Profile**
    - Update personal information
    - Manage payment methods and preferences

### Host Use Cases
1. **Register as Host**
   - Create host account with verification
   - Complete host onboarding process

2. **Create Property Listing**
   - Add property details, photos, and amenities
   - Set pricing and availability rules

3. **Manage Property Listings**
   - Edit property information
   - Update availability calendar
   - Set seasonal pricing

4. **Manage Booking Requests**
   - Review and respond to booking requests
   - Accept, reject, or counter-offer bookings

5. **Track Bookings**
   - View upcoming and past bookings
   - Monitor booking status and guest information

6. **Communicate with Guests**
   - Send and receive messages
   - Provide check-in instructions and support

7. **Manage Calendar**
   - Block dates for maintenance or personal use
   - Update availability in real-time

8. **Review Guests**
   - Rate and review guests after their stay
   - Provide feedback on guest behavior

9. **Manage Payouts**
   - View payment history and pending payouts
   - Update payout preferences and banking information

10. **Respond to Reviews**
    - Reply to guest reviews
    - Address concerns and feedback

### Admin Use Cases
1. **Manage Users**
   - View, suspend, or delete user accounts
   - Handle user verification and disputes

2. **Moderate Content**
   - Review and approve property listings
   - Moderate reviews and messages

3. **Handle Disputes**
   - Mediate conflicts between guests and hosts
   - Process refunds and resolutions

4. **Monitor Platform**
   - Track system performance and usage
   - Generate reports and analytics

5. **Manage Payments**
   - Oversee payment processing and refunds
   - Handle payment disputes and chargebacks

6. **Configure System**
   - Update platform settings and policies
   - Manage fees and commission structures

7. **Content Management**
   - Update terms of service and privacy policies
   - Manage help documentation and FAQs

## System Use Cases

### Core System Processes
1. **User Authentication**
   - Validate user credentials
   - Manage JWT tokens and sessions

2. **Property Search Engine**
   - Index and search property data
   - Apply filters and sorting

3. **Booking Processing**
   - Validate booking requests
   - Check availability and pricing

4. **Payment Processing**
   - Integrate with payment gateways
   - Handle transactions and refunds

5. **Notification System**
   - Send email and SMS notifications
   - Manage notification preferences

6. **Review System**
   - Collect and display reviews
   - Calculate ratings and averages

7. **Communication Hub**
   - Facilitate messaging between users
   - Store message history

8. **Analytics Engine**
   - Collect usage data
   - Generate reports and insights

## Use Case Relationships

### Includes Relationships
- **Create Booking** includes **Validate Availability**
- **Make Payment** includes **Process Transaction**
- **Register Account** includes **Send Verification Email**
- **Create Property Listing** includes **Upload Photos**

### Extends Relationships
- **Advanced Search** extends **Search Properties**
- **Instant Booking** extends **Create Booking**
- **Social Login** extends **Login**
- **Bulk Calendar Update** extends **Manage Calendar**

### Inheritance Relationships
- **Host** inherits from **User** (all basic user functions)
- **Admin** inherits from **User** (all basic user functions)

## Use Case Priorities

### High Priority (MVP)
1. User Registration and Authentication
2. Property Listing and Search
3. Booking Creation and Management
4. Payment Processing
5. Basic Communication

### Medium Priority
1. Review and Rating System
2. Advanced Search Features
3. Calendar Management
4. Notification System

### Low Priority
1. Analytics and Reporting
2. Advanced Admin Features
3. Social Media Integration
4. Mobile App Specific Features

## Success Scenarios and Exceptions

### Typical Success Scenarios
1. **Guest books property**: Search → View Details → Create Booking → Make Payment → Receive Confirmation
2. **Host lists property**: Register → Create Listing → Set Availability → Receive Booking → Confirm
3. **Successful stay**: Check-in → Stay → Check-out → Leave Review → Receive Payout

### Exception Scenarios
1. **Payment Failure**: Retry payment → Contact support → Cancel booking
2. **Booking Conflict**: Notify parties → Find alternative → Process refund
3. **Property Unavailable**: Update availability → Notify guest → Suggest alternatives

## Integration Points

### External Systems
- **Payment Gateway**: Stripe, PayPal integration
- **Email Service**: SendGrid, AWS SES
- **SMS Service**: Twilio, AWS SNS
- **Maps Service**: Google Maps API
- **Cloud Storage**: AWS S3 for image storage

### Internal Systems
- **Database**: User, property, booking, and payment data
- **Cache**: Redis for session and search caching
- **Queue**: Message queues for async processing
- **Logs**: Centralized logging for monitoring

This use case diagram provides a comprehensive view of all interactions within the Airbnb Clone system, serving as a foundation for system design and development planning.
