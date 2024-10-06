SIMPLE ATM SOFTWARE-C#

ATM Machine

        using system;
        class Program
        {
           public static void main()
           {
              int amount = 20000, deposit, withdraw;
              int choice, pin = 0;
              
              Console.WriteLine("Enter Your 4 Digit Pin: ");
        pin = int.Parse(Console.ReadLine());

        while (true)
        {
            Console.WriteLine("\nWELCOME TO YES BANK ATM SERVICE\n");
            Console.WriteLine("1. Current Balance");
            Console.WriteLine("2. Withdraw");
            Console.WriteLine("3. Deposit");
            Console.WriteLine("4. Cancel");
            Console.WriteLine("***************\n");

            Console.WriteLine("ENTER YOUR CHOICE: ");
            choice = int.Parse(Console.ReadLine());

            switch (choice)
            {
                case 1:
                    Console.WriteLine("\nYOUR CURRENT BALANCE IS Rs: {0}", amount);
                    break;

                case 2:
                    Console.WriteLine("\nENTER THE WITHDRAW AMOUNT: ");
                    withdraw = int.Parse(Console.ReadLine());

                    if (withdraw % 100 != 0)
                    {
                        Console.WriteLine("\nPLEASE ENTER THE AMOUNT IN MULTIPLES OF 100");
                    }
                    else if (withdraw > (amount - 1))
                    {
                        Console.WriteLine("\nSORRY! INSUFFICIENT BALANCE");
                    }
                    else
                    {
                        amount -= withdraw;
                        Console.WriteLine("\n\nPLEASE COLLECT YOUR CASH");
                        Console.WriteLine("CURRENT BALANCE IS Rs: {0}", amount);
                    }
                    break;

                case 3:
                    Console.WriteLine("\nENTER THE DEPOSIT AMOUNT: ");
                    deposit = int.Parse(Console.ReadLine());
                    amount += deposit;
                    Console.WriteLine("YOUR AMOUNT HAS BEEN DEPOSITED SUCCESSFULLY.");
                    Console.WriteLine("YOUR TOTAL BALANCE IS Rs: {0}", amount);
                    break;

                case 4:
                    Console.WriteLine("\nTHANK YOU FOR USING YES BANK ATM SERVICE.");
                    return; // Exit the loop and program

                default:
                    Console.WriteLine("\nINVALID CHOICE, PLEASE TRY AGAIN.");
                    break;
            }
        }
    }
}

