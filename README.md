# Scala-Projects

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

                              
