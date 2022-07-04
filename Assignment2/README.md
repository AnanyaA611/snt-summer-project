FUNCTIONS USED and their USE:
1. isOwner() :function to implement a modifier to allow only the owner of the contract to use specific functions
2. constructor(): function to make the creator of the contract the Owner.
3. getCompoundInterest(): function to calculate the amount of Compound interest for given P, R, T
4. reqLoan(): A creditor uses this function to request the Owner to settle his loan, and the amount to settle is calculated using the inputs.
5. getOwnerBalance() : to view the Balance of the contract Owner.
				
The smart contracts are owned by an owner. A smart contract can know its owner’s address using sender property and its available balance using a special built-in object called msg.msg.sender It represents the address that initiated this contract call. 

