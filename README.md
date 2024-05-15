# Scala-Projects


# Project : 1. ATM Machine

### - We are writing a program for an ATM Machine
### - Ask the user to enter the 5 Digit Card Number
### - Ask the user to enter the 4 Digit Pin
### - Ift the user provides the credentials correctly prompt him the following opotions
#### - CHECK BALANCE
#### - WITHDRAW THE AMOUNT
#### - DEPOSIT THE AMOUNT
#### - QUIT THE PROGRAM



# Code solution:-



                    import scala.io.StdIn.readLine
                    import scala.util.control.Breaks._
                    import scala.util.Random
                    
                    object Main{
                  
                      var balance = 1000.0
                      
                      def main(args: Array[String]): Unit = {
                        
                        var Card_number = 12345
                        var digital_pin = 1234
                        
                        var status = Take_Credentials(Card_number,digital_pin)
                        
                        
                        if(status == "success")
                        {
                          get_transaction()
                        }
                        
                      }
                      def get_transaction():Unit={
                  
                        var input = ""
                        do{
                            show_menu()
                            input = readLine("Enter your Options: ")
                            operations(input)
                        }
                        while(input !="4" )
                      }
                  
                  
                      def show_menu():Unit={
                        println("1. CHECK BALANCE")
                        println("2. WITHDRAW CASH")
                        println("3. DEPOSIT CASH")
                        println("4. QUIT THE PROGRAM")
                      }
                      
                      def operations(input:String):Unit={
                            if (input == "1")
                            {
                              check_balance()
                            }
                            else if(input == "2")
                            {
                            var User_amount_withdraw = readLine("Enter the amount to withdraw: ").toInt
                              withdraw_cash(User_amount_withdraw)
                            }
                            else if(input == "3")
                            {
                            var User_amount_deposit = readLine("Enter the amount to deposit: ").toInt
                              deposit(User_amount_deposit)
                            }
                  
                      }
                  
                  
                  
                       def Take_Credentials(Card_number:Int,digital_pin:Int):String={
                  
                        var status = "failed"
                  
                        breakable
                        {
                                for(w <- 1 to 3)
                                {
                                var User_card_number = readLine("Enter your card number: ").toInt
                                var User_pin = readLine("Enter your pin: ").toInt
                  
                                if(User_card_number == Card_number && User_pin == digital_pin)
                                {
                                  status = "success"
                                  println("Valid Informations,Welcome to ATM")
                                  break()
                                }
                                else 
                                {
                                  println("Invalid card number or pin")
                                }
                                }
                        }
                        return status
                      }
                  
                      def check_balance():Unit={
                      println("Your balance is: ")
                      println(balance)
                  
                      }
                      def withdraw_cash(amount:Int):Unit={
                        if(balance < amount)
                        {
                          println("Your balance is NOt Enough: ")
                        }
                        else
                        {
                           println("Amount has been deducted: ")
                          balance = balance - amount
                        }
                      }
                      def deposit(amount:Int):Unit={
                        balance = balance + amount
                        check_balance()
                      }
                    }


### 1. Invalid Credential

   
![Invalid Credential](https://github.com/Reyyadav/Scala-Mini-Project-2/assets/153619494/d7ace90b-fabc-4eca-b333-cf488407c70f)


### 2. Valid Credential


![Valid Credential](https://github.com/Reyyadav/Scala-Mini-Project-2/assets/153619494/635ffbc2-9fe1-4eb0-a92a-0c67852722f4)



### 3. Option 1


![Option 1](https://github.com/Reyyadav/Scala-Mini-Project-2/assets/153619494/bcea6636-cbd4-47bb-8f78-2be8f53b02e2)


### 4. Option 2


![Option 2](https://github.com/Reyyadav/Scala-Mini-Project-2/assets/153619494/6becf4e1-8730-4d83-bb63-6572a35741a1)



### 5. Option 3


![Option 3](https://github.com/Reyyadav/Scala-Mini-Project-2/assets/153619494/7b22efa8-9275-42fd-9d0d-fa0e534df5ae)


### 6. complete transactions


![Option 4](https://github.com/Reyyadav/Scala-Mini-Project-2/assets/153619494/96951d09-adbb-4539-b2ce-445ded67d758)





# Project : 2. Furtune Game 

### -The Player will be given 5 Turns to guess a number lets say "X"
### -After Each Attempt Your Program will do:-
#### -If the player's entered number is less than the actual number X then show the output the player that his guess is less than the actual number X and show him the remaining guess out of 5.
#### -If the player's entered number is Greater than the actual number X then show the output the player that his guess is Greater than the actual number X and show him the remaining guess out of 5.
#### -If he has no tries left show output message player lost the GAME and show him the number X.
#### -If players entered number is equal to X then show output that he won and shoe him th number of tries taken.
### -The Number X will be Between - 0 to 100.


code- 
          
          import scala.io.StdIn.readLine
          import scala.util.control.Breaks._
  
          object Main{
          def main(args: Array[String]): Unit = {
          var X = 50
          var gamestatus = "Lost"
          breakable() 
          {
          for (w <- 1 to 5) 
          {
          var x = readLine("Enter Your Number")
          var guess = x.toInt


        if (guess < X) {
          println("Your guess is less than X")
          println(5 - w)
        } else if (guess > X) {
          println("Your guess is Greater than X")
          println(5 - w)
        } else {
          println("You guessed it Correctly!!")
          println(w)
          gamestatus="Won"
          break()
        }

      }
    }
         if(gamestatus == "Lost")
           println("you lost the Game ")

 
        }
        }


### -Output
### When Lost
![Lost](https://github.com/Reyyadav/scala/assets/153619494/55c0553c-c596-47ec-88d2-7e6258c69d14)

### When Won
![Won](https://github.com/Reyyadav/scala/assets/153619494/9610d462-f0be-4295-b9f1-4f108f135cc5)

When X Actual Number is Generated Randomly

                              import scala.io.StdIn.readLine
                              import scala.util.control.Breaks._
                              import scala.util.Random
                              
                              object Main {
                                def main(args: Array[String]): Unit = {
                                  
                                  var X = Random.nextInt(101)
                                  var gamestatus = "Lost"
                                  breakable() {
                                    for (w <- 1 to 5) {
                                      var x = readLine("Enter Your Number")
                                      var guess = x.toInt
                              
                                      if (guess < X) {
                                        println("Your guess is less than X")
                                        println(5 - w)
                                      } else if (guess > X) {
                                        println("Your guess is Greater than X")
                                        println(5 - w)
                                      } else {
                                        println("You guessed it Correctly!!")
                                        println(w)
                                        println(X)
                                        gamestatus="Won"
                                        break()
                                      }
                              
                                    }
                                  }
                                       if(gamestatus == "Lost")
                                       println(X)
                                         println("you lost the Game ")
                              
                               
                                }
                              
                              }


### Code

- ![Code](https://github.com/Reyyadav/scala-Mini-Project/assets/153619494/b173b7e1-6a56-42e5-a413-08229df4ac5c)

                              
