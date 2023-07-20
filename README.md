# Flight-Management-System
The given code is a C++ program for a flight management system. It allows users to book flights, view available flight routes, register complaints, and manage flight bookings. It contains several classes, each with different functionalities related to flight booking and management.
Overall, the code is a basic implementation of a flight management system for a fictional airline called "High Fly." The system allows users to book flights, view available flight routes, register complaints, and provides information about the airline. Below is a summary of the main functionalities:

1. Booking Flights:
   - Users can book both local and international flights.
   - For local flights, users can select the origin and destination, choose between business and economy class, select the number of seats, and choose a meal type.
   - For international flights, users need to provide their passport number for verification.
   - The system checks the validity of the chosen destination and calculates the total payment for the booking.
   - After booking, the ticket information is saved to a file, and users can view and confirm their bookings.

2. Available Flight Routes:
   - The system displays available flight routes for both local and international destinations.
   - Users can choose to book a flight or exit to the main menu.

3. Complaint Registration:
   - Users can register complaints about different aspects of the airline service, such as airport handling, baggage delivery, booking and ticketing, or other issues.
   - Users provide their name, phone number, and the details of the complaint, which are saved to a text file.

4. About Information:
   - The system provides information about the airline, including its history and services.

5. Manage Bookings:
   - Users can manage their flight bookings, allowing them to change the date of their booked flight or cancel the booking.

However, the code does have some limitations and potential issues:
- It uses non-standard headers and functions, which can lead to portability issues across different platforms.
- Input validation is limited, leaving room for potential errors if users enter invalid input.
- File handling lacks robust error handling and data validation.
- The code structure and organization could be improved for better maintainability and readability.

Overall, the code serves as a basic demonstration of a flight management system but would require further refinement and enhancements to make it suitable for real-world use.
Let's go through the details of each class and its functions:

1. `class passenger`:
   - This is an abstract base class that defines common data members and pure virtual functions that will be overridden in derived classes.
   - Data Members:
     - `bseats`: A constant integer representing the total number of business class seats available.
     - `eseats`: A constant integer representing the total number of economy class seats available.
     - `firstname`: A string to store the first name of the passenger.
     - `lastname`: A string to store the last name of the passenger.
     - `phone`: A string to store the phone number of the passenger.
     - `mealtype`: A string to store the meal type selected by the passenger.
     - `passport`: A string to store the passport number of the passenger (for international flights).
     - `Address`: A string to store the address of the passenger.
     - `bus`: An integer representing the number of available business class seats.
     - `eco`: An integer representing the number of available economy class seats.
     - `datedep`: An integer representing the date of departure in the format DDMMYYYY.
     - `payment`: An integer representing the total payment for the booking.

   - Pure Virtual Functions:
     - `ldest()`: Checks if the local destination is valid and calculates the payment for the booking.
     - `idest(string pass)`: Checks if the international destination is valid and calculates the payment for the booking.
     - `seats()`: Allows the user to choose the class (business or economy) and number of seats for booking.
     - `Meals()`: Allows the user to select the meal type for the booking.
     - `Registration()`: Registers the passenger's booking and writes the ticket information to a file.
     - `display()`: Displays the ticket information from the file and confirms the booking status.
     - `drive()`: Allows the user to request a pick-up and drop-off service.

2. `class booking` (Derived from `class passenger`):
   - This class implements the virtual functions of the base class for booking a flight.
   - Constructor: Initializes the base class using member initializer list and sets some specific data members.

3. `class Manage`:
   - This class handles management actions such as changing the date or canceling a flight booking.
   - Functions:
     - `change()`: Allows the user to change the date of the booked flight or cancel the booking.

4. `class about`:
   - This class provides information about the airline.
   - Functions:
     - `Aboutus()`: Displays information about the airline.

5. `class complain`:
   - This class allows users to register a complaint.
   - Constructor: Initializes the passenger's data for registering a complaint.
   - Functions:
     - `type()`: Allows the user to choose the type of complaint and registers it.

6. `class routes`:
   - This class provides information about available flight routes.
   - Functions:
     - `print()`: Displays available flight routes and asks the user if they want to book a flight.

7. `int main()`:
   - The main function is the entry point of the program.
   - It initializes the system and presents the main menu to the user.
   - Based on the user's choice, it performs different operations using the classes and functions defined above.

Note: The code contains several legacy headers like `conio.h`, `unistd.h`, and `stdio.h`, which are not part of standard C++ and might cause portability issues. The code also uses functions like `getch()` and `sleep()` that are not standard C++ functions. It is essential to ensure proper handling and portability while using such non-standard functions and headers in C++ programs.
