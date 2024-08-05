# Queue Simulation in COBOL

This COBOL program simulates the operation of a single service bay at "Speedy's Auto Repair." The program measures both the average service time (from arrival to completion) and the length of the queue at the arrival of each customer. The events in this system consist of arrivals and departures.

## Program Structure

The program consists of the following main sections:

1. **Initialization**
2. **Event Handling (Arrivals and Departures)**
3. **Queue Management**
4. **Statistics Collection**
5. **Output Results**

## Key Variables

- **CURRENT-TIME**: The current simulation time.
- **NEXT-ARRIVAL-TIME**: The time of the next customer arrival.
- **NEXT-DEPARTURE-TIME**: The time of the next service completion.
- **NEXT-SERVICE-TIME**: The service time for the next customer.
- **SERVICE-BAY-BUSY**: Indicates if the service bay is busy (`"Y"`) or not (`"N"`).
- **TOTAL-CUSTOMERS**: The total number of customers served.
- **TOTAL-SERVICE-TIME**: The cumulative service time of all customers.
- **AVERAGE-SERVICE-TIME**: The average service time per customer.
- **QUEUE-LENGTH**: The current length of the queue.
- **AVERAGE-QUEUE-LENGTH**: The average queue length.
- **WAITING-QUEUE**: An array to store the arrival times of customers in the queue.
- **SEED**: The seed for the random number generator.
- **RAND-NUM**: The generated random number.

## Procedure Division

### START-SIMULATION

This is the main entry point of the program. It performs the following tasks:

1. **INITIALIZE-SEED**: Initializes the random seed using the current time.
2. **INITIALIZE-VARIABLES**: Sets up initial conditions for the simulation.
3. **ADVANCE-TIME-TO-NEXT-EVENT**: Advances the simulation time to the next event.
4. **HANDLE-ARRIVAL**: Handles customer arrivals.
5. **HANDLE-DEPARTURE**: Handles service completions.
6. **OUTPUT-RESULTS**: Outputs the simulation results.

### INITIALIZE-SEED

Uses the `ACCEPT` statement to get the current time and initialize the seed for the random number generator.

### INITIALIZE-VARIABLES

Sets initial values for key variables and generates the first arrival time.

### ADVANCE-TIME-TO-NEXT-EVENT

Advances the simulation time to either the next arrival time or the next departure time, whichever is sooner.

### GENERATE-RANDOM-NUMBER

Generates a random number using a linear congruential generator.

### GENERATE-NEXT-ARRIVAL

Generates the time for the next customer arrival based on a random interval.

### GENERATE-SERVICE-TIME

Generates the service time for the next customer based on a random duration.

### HANDLE-ARRIVAL

Handles the arrival of a new customer, adding them to the queue and starting service if the bay is not busy.

### START-SERVICE

Starts servicing the next customer in the queue.

### HANDLE-DEPARTURE

Handles the completion of a service, moving the next customer in the queue to the service bay.

### MOVE-QUEUE-FORWARD

Moves the queue forward after a customer is serviced.

### OUTPUT-RESULTS

Displays the total number of customers, average service time, and average queue length at the end of the simulation.

## Running the Program

To compile and run the program, use the following commands:

```sh
cobc -x queue-simulation.cob
./queue-simulation

## Example Output
TOTAL CUSTOMERS: 00100
AVERAGE SERVICE TIME: 0000000044.94
AVERAGE QUEUE LENGTH: 00000.01

## Screenshot
