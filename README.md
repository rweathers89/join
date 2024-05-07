
﻿## Project Description

The Join app is a progressive web application with a serverless backend,
offering offline access to upcoming events in specific cities. Its responsive design
ensures seamless display across devices, delivering a superior user experience.
Powered by Test-Driven Development, it prioritizes code quality and test coverage for optimal performance.

### User Stories

1. As a user, I should be able to see or hide event details so that I can see the details of events taking place.

2. As a user, I should be able to see the number of events taking place, so that I can quickly find an event.

3. As a user, I should be able to use the app when I'm offline so that I can have a list of events at any time. 

4. As a user, I should be able to add an app shortcut to the Home Screen of my phone, so that I have easy access to the app.

5. As a user I should be able to see charts visualizing event details, so that I can easily compare data for that event. 

6. As a user, I should be able to filter events by city, so that I can see events in a particular city.


### Scenarios

1. Scenario: Show upcoming events from all cities when user hasn't searched for a city
    Given the user hasn't searched for any city
    When the user views upcoming events
    Then the app displays upcoming events from all cities

2. Scenario: User should see a list of suggestions when they search for a city
    Given the user is on the city search screen
    When the user starts typing a city name
    Then the app displays a list of suggestions matching the entered city name

3. Scenario: User can select a city from the suggested list
    Given the user has entered a city name and is viewing the list of suggestions
    When the user selects a city from the suggestions
    Then the app filters events based on the selected city

4. Scenario: An event element is collapsed by default
    Given an event is displayed on the app
    Then the event details are initially collapsed

5. Scenario: User can expand an event to see details
    Given an event is displayed with collapsed details
    When the user interacts with the event to expand details
    Then the event details are shown

6. Scenario: User can collapse an event to hide details
    Given an event is displayed with expanded details
    When the user interacts with the event to collapse details
    Then the event details are hidden

7. Scenario: When user hasn’t specified a number, 32 events are shown by default
    Given the user hasn't specified a number of events to display
    When the user views the events page
    Then the app displays 32 events by default

8. Scenario: User can change the number of events displayed
    Given the user is viewing the events page
    When the user specifies a different number of events to display
    Then the app updates the events page to show the specified number of events

9. Scenario: Show cached data when there’s no internet connection
    Given the app is offline
    When the user tries to access event data
    Then the app displays cached event data

10. Scenario: Show error when user changes search settings (city, number of events)
    Given the app is offline
    When the user attempts to change search settings such as city or number of events
    Then the app displays an error message indicating inability to update settings due to lack of internet connection
11. Scenario: User can install the meet app as a shortcut on their device home screen
    Given the user is accessing the meet app through a supported browser on their device
    When the user accesses the browser menu options
    And selects the "Add to Home Screen" option
    Then the meet app shortcut is installed on the device's home screen
12. Scenario: Show a chart with the number of upcoming events in each city
    Given the user is viewing the event statistics section
    When the user selects the option to view upcoming events by city
    Then the app generates and displays a chart showing the number of upcoming events in each city



### Run this project locally
- Go to the project directory

      cd project-folder

- Install dependencies

      npm install

- Run on localhost:3000

      npm run start

**USE OF SERVERLESS FUNCTION (FaaS) IN THE JOIN APP**

These serverless functions will be responsible for securely managing user access, obtaining and refreshing OAuth2 tokens, and ensuring the security of interactions between your React application and the Google Calendar API.
AWS Lambda will be the chosen cloud-service provider for implementing these serverless functions, making the app's architecture more scalable according to user demand and cost-effective.
