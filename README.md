# 4th-
polymorphism
import java.util.*;

abstract class Vehicle {
    String vehicleNumber, brand;
    Vehicle(String n, String b){ vehicleNumber=n; brand=b; }
    abstract void startEngine();
    final void showVehicleIdentity(){
        System.out.println("Vehicle Number : "+vehicleNumber);
        System.out.println("Brand          : "+brand);
    }

    public static void main(String[] args){
        Scanner sc=new Scanner(System.in);
        System.out.println("Enter Car Details");
        System.out.print("Number: "); String cNo=sc.nextLine();
        System.out.print("Brand: "); String cBr=sc.nextLine();
        Car c=new Car(cNo,cBr);
        System.out.println("\nEnter Bike Details");
        System.out.print("Number: "); String bNo=sc.nextLine();
        System.out.print("Brand: "); String bBr=sc.nextLine();
        Bike b=new Bike(bNo,bBr);
        System.out.println("\n--- CAR DETAILS ---");
        c.startEngine(); c.showVehicleIdentity();
        System.out.println("\n--- BIKE DETAILS ---");
        b.startEngine(); b.showVehicleIdentity();
    }
}

class Car extends Vehicle {
    Car(String n,String b){ super(n,b); }
    void startEngine(){ System.out.println("Car engine started with key ignition."); }
}

class Bike extends Vehicle {
    Bike(String n,String b){ super(n,b); }
    void startEngine(){ System.out.println("Bike engine started with self start."); }
}
