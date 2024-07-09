This Solidity contract demonstrates basic error handling using require, assert, and revert statements. It includes functionality to set a value and perform division with appropriate error checks.

Features:
setValue: Sets a public state variable value with input validation.

performDivision: Performs division of two numbers with error handling for zero denominators and indivisible numerators.

Contract Details
State Variable
uint public value;
Stores a value that is publicly accessible.
Functions
setValue(uint _value)
Sets the state variable value to a specified _value.

Parameters:
uint _value: The new value to set.

Error Handling:
require(_value > 0, "Value must be greater than 0.");
Ensures the input value _value is greater than zero.

assert(value != _value);
Ensures the new value is different from the current value.

performDivision(uint _numerator, uint _denominator)
Performs division of two numbers with error handling.

Parameters:
uint _numerator: The numerator for division.
uint _denominator: The denominator for division.
Returns:
uint: The result of the division.
Error Handling:
require(_denominator != 0, "Cannot divide by zero.");
Ensures the denominator is not zero.
if (_numerator % _denominator != 0) { revert("Numerator must be divisible by denominator"); }
Reverts the transaction if the numerator is not divisible by the denominator.
Usage
Prerequisites
Install Remix IDE or use any other Solidity development environment.
Steps
Compile the Contract:

Open Remix IDE.
Create a new file ErrorHandlingContract.sol and paste the contract code.
Select the appropriate compiler version (0.8.1).
Compile the contract.
Deploy the Contract:

Go to the "Deploy & Run Transactions" tab.
Ensure the environment is set to "JavaScript VM (London)".
Deploy the ErrorHandlingContract.
Interact with the Contract:

Use the setValue function to set a positive value.
Attempt to set the value to zero or the same value to see the require and assert statements in action.
Use the performDivision function to divide two numbers.
Try dividing by zero or using a numerator not divisible by the denominator to see the require and revert statements in action.


Example
Here’s an example of how to use the contract functions:

Set Value:
Call setValue(10) to set the value to 10.
Attempt to call setValue(0) to trigger the require error.
Attempt to call setValue(10) again to trigger the assert error.
Perform Division:

Call performDivision(10, 2) to get the result 5.
Attempt to call performDivision(10, 0) to trigger the require error.
Attempt to call performDivision(10, 3) to trigger the revert error.
License
