# Exercise 3: BookTrip

This example illustrates creating a bot that is configured to support multiple intents. The example also illustrates how you can use session attributes for cross-intent information sharing. After creating the bot, you use a test client in the Amazon Lex console to test the bot (BookTrip).

The BookTrip bot in this example is configured with two intents (BookHotel and BookCar). For example, suppose a user first books a hotel. During the interaction, the user provides information such as check-in dates, location, and number of nights. After the intent is fulfilled, the client can persist this information using session attributes.

Now suppose that the user continues to book a car. Using information that the user provided in the previous BookHotel intent (that is, destination city, and check-in and check-out dates), the code hook (Lambda function) you configured to initialize and validate the BookCar intent, initializes slot data for the BookCar intent (that is, destination, pick-up city, pick-up date, and return date). This illustrates how cross-intent information sharing enables you to build bots that can engage in dynamic conversation with the user. 

In this example, we use the following session attributes. Only the client and the Lambda function can set and update session attributes. Amazon Lex only passes these between the client and the Lambda function. Amazon Lex doesn't maintain or modify any session attributes.

+ `currentReservation` – Contains slot data for an in-progress reservation and other relevant information.

+ `lastConfirmedReservation` – Contains similar information for a previous intent, if any. For example, if the user booked a hotel and then is in process of booking a car, this session attribute stores slot data for the previous BookHotel intent.

+ `confirmationContext` – The Lambda function sets this to `AutoPopulate` when it prepopulates some of the slot data based on slot data from the previous reservation (if there is one). This enables cross-intent information sharing. For example, if the user previously booked a hotel and now wants to book a car, Amazon Lex can prompt the user to confirm (or deny) that the car is being booked for the same city and dates as their hotel reservation

In this exercise you use blueprints to create an Amazon Lex bot and a Lambda function.

**Video Reference**  
https://www.youtube.com/playlist?list=PL7dtPnQuxetLDXL13ucdD_KTnfXqEE4K3

**Next Step**  
[Step 1: Review the Blueprints Used in this Exercise](ex3-step1.md)
