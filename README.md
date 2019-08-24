# CoreJava_Topics

Interface Vs Abstract

  An interface consists of singleton variables (public static final) and public abstract methods. We normally prefer to use an interface in real time when we know what to do but don't know how to do it.
  
This concept can be better understood by example:

Consider a Payment class. Payment can be made in many ways, such as PayPal, credit card etc. So we normally take Payment as our interface which contains a makePayment() method and CreditCard and PayPal are the two implementation classes.

public interface Payment { 

 void makePayment();//by default it is a abstract method
 
} 
 
 public class PayPal implements Payment {
    public void makePayment() { 
      //some logic for PayPal payment //e.g. Paypal uses username and password for payment 
      } } 
      
 public class CreditCard implements Payment { 
      public void makePayment() { //some logic for CreditCard payment //e.g. CreditCard uses card number, date of expiry etc...
      } }
      
In the above example CreditCard and PayPal are two implementation classes /strategies. An Interface also allows us the concept of multiple inheritance in Java which cannot be accomplished by an abstract class.

We choose an abstract class when there are some features for which we know what to do, and other features that we know how to perform.
Consider the following example:

public abstract class Burger {
   public void packing() { //some logic for packing a burger }
    public abstract void price(); //price is different for different categories of burgers 
}
 
 public class VegBerger extends Burger { 
    public void price() { 
       //set price for a veg burger.
    } 
  } 

public class NonVegBerger extends Burger { 
      public void price() {
      //set price for a non-veg burger.
      } 
 }

If we add methods (concrete/abstract) in the future to a given abstract class, then the implementation class will not need a change its code. However, if we add methods in an interface in the future, we must add implementations to all classes that implemented that interface, otherwise compile time errors occur.
