# 12 Reasons your API Sucks
@speaker Keith Casey @caseysoftware
@date 2014-04-25
@deck joind.in/10800

## Overview
Those first moments of using an API are pivotal. There’s nothing like downloading this week’s PDF of the documentation, setting up a SOAP client, reconfiguring all your URLs, and decoding the latest binary payloads. It makes your heart sing and your blood pressure rise. Just like there are code smells through the rest of your project, there are API smells that make them hard to design, hard to launch, and hard to maintain. We’ll use this time to explore a few common APIs to highlight those issues and demonstrate strategies to fix the issues before they become problems.

## Book
The Practical Approach to API Design
theAPIDesignBook.com
coupon code: lsp14 (10% off)

## DX (DevEx, Developer Experience)
Developer Experience is to Developers as User Experience is to Users

>> "Don't make me Think!"
- The faster you can get someone started the more likely you are to win!

## Love at first Byte!
### 1. Documentation
- Ways to deliver documentation
	- PDFs (redacted)
	- HTML (https://www.twilio.com/docs/api/rest)
- Make it freely available
- Make it Interactive!
	- Swagger (https://api-beta.op3nvoice.com/docs)
	- iodocs (http://developer.rottentomatoes.com/io-docs)
	- Example: **Marvel**

### 2. Incomplete/Wrong Documentation
>> Helper Documentation != API Documentation

### 3. "Getting Started" Code
- Provide sample code to get API users started
- Should be able to copy/paste/run

### 4. Too much boilerplate code
- keep sample code short and to the point
- KISS - Keep It Simple Stupid

### 5. SOAP as the interface
- SOAP is not very discoverable
- difficult to crawl/discover available resources

>> REST is like borrowing $10 from a friend
>> SOAP is like a mortgage

## Adoption
### Who is the API for?
- Is this an internal API that was released publicly?
- Is this an API specifically built for external use?
- Where does the API fit into their business?
	- aka _Is it bolted on or a key part of the company?_

>> Twilio makes money when you use their service.
_The faster developers can use the API, the faster Twilio makes money_

### 6. Illogical/Inconsistencies
- URIs need to be uniquely addressable resources. Human friendly URIs are nice, but not necessary

### 7. Poor Workflow & Modeling
- Affordances
	- What is the API producer's goal?
	- What problem(s)/task(s) does it make simple?
	- What do you want to do?

>> Define interactions

**Sorting Cards (ecom)**
- Steps (add to cart, update qty's, etc)
- Participants (user, storefront, merchant/payment gateway)
- Groupings (logical groupings)

>> CRUD is simply mapping resources to the existing Data Model. Instead, map resources to business steps/logic to make it more useful

### 8. Numerous Approaches
>> Swiss Army Knife
When there are multiple ways to do something, you are making it unnecessarily difficult/complicated for your API users.
One definitive answer simplifies things.

### 9. Payloads
- consistencies with headers and response codes

### 10. Authentication
- Don't roll your own methods

## Day To Day Operations
### 11. Error Messages
>> 404: "There was an error"
- Make logical and helpful error codes
- Make response action and response codes consistent with proper response (don't send a 200 code for an error)

**Error Codes**
- Integrating error codes allows you to "extend" where HTTP "falls off" (404 just kind of drops off...there was an error, but why)
- Allows you to pass back really detailed error messages

>> Don't rebuild HTTP

### 12. Logging and Debugging
- Runscope (sits b/w "you" and the API and records everything in between)

## Putting It All Together
**Documentation**
- Consumable
- Accurate

**Adopting**
- Logical
- Designed workflows vs Random Junk
- One True Way
- Consistent Payloads
- Don't roll your own Auth

**Supporting**
- Error Messages
- Logging & Debugging
