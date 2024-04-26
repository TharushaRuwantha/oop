<h3>Student / Course / Student App Question</h3>
<h4>Student class code</h4>

```bash
public class Student {
	private String name;
	private int age;		
	
	public String getName() {
		return name;
	}

	public int getAge() {
		return age;
	}

	public Student(String name, int age) {
		this.name=name;
		this.age=age;
	}
	
	public void displayInfo() {
		System.out.println("name : " + name);
		System.out.println("age : " + age);		
	}
}
```

<h4>Course class code</h4>

```bash
public class Course extends Student {
	
	private String courseName;

	public Course(String name, int age, String courseName) {
		super(name, age);
		this.courseName = courseName;		
	}
	
	public void displayCourseInfor() {
		System.out.println("name : " + getName());
		System.out.println("age : " +getAge());
		System.out.println("course Name : " + courseName);
	}	
}
```

<h4> Student App</h4>

```bash
public class StudentApp {

	public static void main(String[] args) {
		
		Course course1 = new Course("Alice" , 20 , "Java Programming");
		Course course2 = new Course("Yashmi", 18, "Maths");
		
		course1.displayInfo();
		course2.displayInfo();
	}

}
```
----------------------------------------------------------------------------------------------------
<h3>celsius  Fahrenheit Question</h3>
<h4>TemperatureConverter class code</h4>

```bash
public class TemperatureConverter {
	private double temperature;
	
	public TemperatureConverter(){
		this.temperature=0;
	}

	public double getTemperature() {
		return temperature;
	}
	
	public double celsiusToFahrenheit(double celsius) {
		temperature = (celsius * 9/5) + 32;
		return(temperature);		
	}
	
	public double fahrenheitToCelsius(double fahrenheit) {
		temperature = (fahrenheit - 32) * 5/9;
		return (temperature);	
	}
}
```

<h4>TempApp</h4>

```bash
import java.util.*;

public class TempApp {

	public static void main(String[] args) {
		
		Scanner takeInput = new Scanner(System.in);
		
		double celsius;
		double fahrenhei;
		
		TemperatureConverter convert1 = new TemperatureConverter();
		TemperatureConverter convert2 = new TemperatureConverter();
		
		System.out.print("Enter the temperature in celsius : ");
		celsius=takeInput.nextDouble();
		
		System.out.print("Enter the temperature in fahrenhei : ");
		fahrenhei=takeInput.nextDouble();
		
		double fah = convert1.celsiusToFahrenheit(celsius);
		double cel = convert2.fahrenheitToCelsius(fahrenhei);
		
		System.out.println(celsius + "Celsius is equal to " + fah + "Fahrenheit");
		System.out.println(fahrenhei + "Fahrenheit is equal to " + cel + "Celsius");	

	}

}
```

----------------------------------------------------------------------------------------------------

<h3>factorial Question</h3>
<h4> MathOperations class code</h4>

```bash
import java.util.*;

public class MathOperations {
	
	public void drawMultiplicationTable(int number, int range) {
		for (int i=1; i <= range; i ++) {
			System.out.println(number + " x " + i + " = " + i * number  );	
			
		}
	}
	
	public int factorial() {
		Scanner takeInput = new Scanner(System.in);
		
		int num;
		
		System.out.print("Enter Positive integer : ");
		num=takeInput.nextInt();
		
		takeInput.close();
		
		int factorial =1;
		
		for (int i=2; i<=num; i++) {
			factorial=factorial*i;
			
		}
		
		return factorial;
	}

}
```

<h4> MathApp class code</h4>

```bash
public class MathApp {

	public static void main(String[] args) {
		
		MathOperations d1 = new MathOperations();
		d1.drawMultiplicationTable(2, 5);
		
		
		int fac = d1.factorial();
		
		System.out.print(fac);

	}

}
```


----------------------------------------------------------------------------------------------------

<h3>Car vehicle motoecycle Question</h3>
<h4>Car class code</h4>

```bash
public class Car extends Vehicle {
	
	int numSeats;
	
	

	public int getNumSeats() {
		return numSeats;
	}



	public void setNumSeats(int numSeats) {
		this.numSeats = numSeats;
	}



	public Car(String Model, double RentalPricePerDay,int numSeat) {
		super(Model, RentalPricePerDay);
		this.numSeats=numSeat;
			
	}
}
```

<h4>Motorcycle class code</h4>

```bash

public class Motorcycle extends Vehicle {
	int engineCapaity;

	public Motorcycle(String Model, double RentalPricePerDay, int engineCapacity) {
		super(Model, RentalPricePerDay);
		this.engineCapaity=engineCapacity;
				
	}

}
```

<h4>Vehicle class code</h4>

```bash
public class Vehicle {
	String model;
	double rentalPricePerDay;
	
	public String getModel() {
		return model;
	}

	public void setModel(String model) {
		this.model = model;
	}

	public double getRentalPricePerDay() {
		return rentalPricePerDay;
	}

	public void setRentalPricePerDay(double rentalPricePerDay) {
		this.rentalPricePerDay = rentalPricePerDay;
	}
	
	public Vehicle(String Model,double RentalPricePerDay) {
		this.model = Model;
		this.rentalPricePerDay = RentalPricePerDay;
	}
	
	//method
	public double calculateRentalCost(int days) {
		return rentalPricePerDay * days;
		
	}
}
```

<h4>Main class code</h4>

```bash
public class Main {

	public static void main(String[] args) {
		
		Car c1 = new Car("Toyota",50.5,4);
		Motorcycle m1 = new Motorcycle("Scooter",30.5,200);
		
		System.out.println(c1.calculateRentalCost(5));
		System.out.println(m1.calculateRentalCost(2));

	}

}
```

----------------------------------------------------------------------------------------------------
<h3>Employee paartime emloyee Question</h3>
<h4>Employee class code</h4>

```bash
public class Employee {
	private String name;
	private double salary;


	
	
	public Employee(String Name, double Salary) {
		this.name=Name;
		this.salary=Salary;
	}
	
	public void displayInfor() {
		System.out.println(name);
		System.out.println(salary);
	}

}
```
<h4>ParttimeEmployee class code</h4>

```bash
public class ParttimeEmployee extends Employee {
	private int OTHrs;

	public ParttimeEmployee(String Name, double Salary, int othrs) {
		super(Name, Salary);
		this.OTHrs=othrs;
		
	}
	
	public void displayEmpInfor() {
		displayInfor();
		System.out.println(OTHrs);
	}

}
```
<h4>EmpApp class code</h4>

```bash
public class EmpApp {

	public static void main(String[] args) {
		
		ParttimeEmployee emp1= new ParttimeEmployee("Alice",2000.00,7);
		ParttimeEmployee emp2= new ParttimeEmployee("yashmi",1000.00,8);
		emp1.displayEmpInfor();
		emp2.displayEmpInfor();

	}

}
```

----------------------------------------------------------------------------------------------------

<h3>Vehicle / Car / Motorcycle  Question</h3>

<h4>Vehicle class code</h4>

```bash
public class Vehicle {
	String model;
	double rentalPricePerDay;
	
	public String getModel() {
		return model;
	}

	public void setModel(String model) {
		this.model = model;
	}

	public double getRentalPricePerDay() {
		return rentalPricePerDay;
	}

	public void setRentalPricePerDay(double rentalPricePerDay) {
		this.rentalPricePerDay = rentalPricePerDay;
	}


	
	public Vehicle(String Model,double RentalPricePerDay) {
		this.model = Model;
		this.rentalPricePerDay = RentalPricePerDay;
	}

	
	//method
	public double calculateRentalCost(int days) {
		return rentalPricePerDay * days;
		
	}
}
```

<h4>Car class code</h4>

```bash
public class Car extends Vehicle {
	
	int numSeats;
	
	

	public int getNumSeats() {
		return numSeats;
	}



	public void setNumSeats(int numSeats) {
		this.numSeats = numSeats;
	}



	public Car(String Model, double RentalPricePerDay,int numSeat) {
		super(Model, RentalPricePerDay);
		this.numSeats=numSeat;
			
	}

}

```

<h4>Motorcycle class code</h4>

```bash
public class Motorcycle extends Vehicle {
	int engineCapaity;

	public Motorcycle(String Model, double RentalPricePerDay, int engineCapacity) {
		super(Model, RentalPricePerDay);
		this.engineCapaity=engineCapacity;
		
		
	}

}
```
<h4>main class code</h4>

```bash
public class Main {

	public static void main(String[] args) {
		
		Car c1 = new Car("Toyota",50.5,4);
		Motorcycle m1 = new Motorcycle("Scooter",30.5,200);
		
		System.out.println(c1.calculateRentalCost(5));
		System.out.println(m1.calculateRentalCost(2));

	}

}
```


