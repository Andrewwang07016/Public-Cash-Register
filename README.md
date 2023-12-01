# Cash-Register
// Cash register with quantity and tax

#include <iostream>
#include <iomanip>
using namespace std;

int main()
{
	// Declares and initializes variables 
 	double cashDrawer = 500.00;
	int productID = 0;
	int quantity = 0;
	double price = 0.0;
	double subtotal = 0.0;
	double salesTax = 0.0;
	double totalSale = 0.0;
	int anotherSale = 1;
	double taxRate = 0.0;
	double allSale = 0.0;

	// Creates a do loop for repeating sales
	do
	{
	
		// Enter the first Product ID for the first sale (-1 to exit)
		cout << "Enter the first Product ID (-1 to exit): ";
		cin >> productID;
  
		// Main loop for each sale (while() loop (-1 to exit))
		while (productID != -1)
  
		{
			// Asks user to enter the quantity
			cout << "Enter the quantity: ";
			cin >> quantity;


			// Switch statement to determine the price, and calculate sales tax, if any, for the item.
			switch (productID)
			{
			case 101:
				price = 65.00;
				taxRate = 0.075;
				break;
			case 102:
				price = 12.50;
				taxRate = 0.00;
				break;
			case 103:
				price = 24.50;
				taxRate = 0.00;
				break;
			case 104:
				price = 38.75;
				taxRate = 0.075;
				break;
			case 105:
				price = 17.80;
				taxRate = 0.075;
				break;
			case 106:
				price = 16.50;
				taxRate = 0.00;
				break;
			case 107:
				price = 42.85;
				taxRate = 0.075;
				break;
			case 108:
				price = 32.99;
				taxRate = 0.075;
				break;
			case 109:
				price = 28.75;
				taxRate = 0.075;
				break;
			case 110:
				price = 51.55;
				taxRate = 0.00;
			default:
				cout << "Error: Product ID not found. Must be between 101-110." << endl;


			}

			// Calculations to calculate the subtotal, salesTax, totalSale, and allSale
			subtotal += quantity * price;
			salesTax += quantity * price * taxRate;
			totalSale = subtotal + salesTax;
			allSale += subtotal + salesTax;


			// Gets the next Product ID
			cout << "Enter the next Product ID (-1 to exit): ";
			cin >> productID;


		} // end while loop


		// Prints and properly formatted output for each sale
		cout << "Subtotal:   $" << fixed << subtotal << setprecision(2) << endl;
		cout << "Sales Tax:  $" << fixed << salesTax << setprecision(2) << endl;
		cout << "Total Sale: $" << fixed << totalSale << setprecision(2) << endl;
		subtotal = 0.00;
		salesTax = 0.00;
		totalSale = 0.00;



		// Asks if there is another sale
		cout << "Is there another sale? (1 to continue, 0 to end)" << endl;
		cin >> anotherSale;

	} while (anotherSale == 1);
		
		
	// Displays how much is in the cash drawer at the end
	cout << "Total in Cash Drawer is: $" << cashDrawer + allSale << setprecision(2) << endl;

	// Program exit, indicates if the program was executed successfully
 	return 0;
		
}
