# Secure-Password-Validator-with-C-Programming
using System;

class MainClass {

  public static string StringChallenge(string str) {

    // code goes here  
    bool hasCapitalLetter = false;
    foreach(char c in str){
      if(char.IsUpper(c)){
        hasCapitalLetter = true;
        break;
      }
    }

    bool hasNumber = false;
    foreach(char c in str){
      if(char.IsDigit(c)){
        hasNumber = true;
        break;
      }
    }

    bool hasSpecialCharacter = false;
    foreach(char c in str){
      if(char.IsPunctuation(c) || char.IsSymbol(c)){
        hasSpecialCharacter = true;
        break;
      }
    }

    bool containdPassword = str.ToLower().Contains("password");
    bool isLengthValid = str.Length > 7 && str.Length < 31;
    if(hasCapitalLetter && hasNumber && hasSpecialCharacter && !containdPassword && isLengthValid){
      return "true";
    }
    else{
      return "false";
    }


    //return str;

  }

  static void Main() {  

    // keep this function call here
    Console.WriteLine(StringChallenge(Console.ReadLine()));
    
  } 

}
