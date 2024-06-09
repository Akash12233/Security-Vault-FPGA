WORKING:-
The Verilog code implements a security vault system controlled by a finite state machine (FSM) with 
distinct states and transitions. Here's how it works:
1. Initialization:
 - Upon reset (`reset_n` signal), the system initializes to the IDLE state. All LEDs are turned 
off, and the current state is set to IDLE.
2. State Transition:
 - The FSM transitions between states based on inputs and the current state.
 - In the IDLE state, if someone enters (`sensor_entrance` signal), it transitions to the 
WAIT_PASSWORD state.
3. Password Entry:
 - In the WAIT_PASSWORD state, the system waits for a predefined duration 
(`counter_wait`) before checking the entered password.
 - If the correct password (`password_1` and `password_2`) is entered within the time limit, 
it transitions to the RIGHT_PASS state; otherwise, it goes to the WRONG_PASS state.
4. System Behavior:
 - In the RIGHT_PASS state, the system blinks the green LED to indicate successful access.
 - If someone exits (`sensor_exit` signal) while in the RIGHT_PASS state, it returns to the 
IDLE state.
 - If both entrance and exit sensors are active, it transitions to the STOP state.
 - In the STOP state, it continuously blinks the red LED until the correct password is entered 
again, preventing further access.
5. LED Output:
 - LED outputs (`RED_LED` and `GREEN_LED`) reflect the system's state, providing 
visual feedback to users.
![WhatsApp Image 2024-04-22 at 14 22 03](https://github.com/Akash12233/Security-Vault-FPGA/assets/121252393/322f8502-203d-4193-a1a3-6f51df3a0629)

`Project Report` :https://drive.google.com/file/d/1O5SnSSdRiz8tldTs2gE2HY6uC1a7dmNr/view?usp=sharing
