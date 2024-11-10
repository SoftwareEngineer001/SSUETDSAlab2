# SSUETDSAlab2

*public class lab2MuhammadTalha {
    static class Color {
        private int red;
        private int green;
        private int blue;

        public Color(int red, int green, int blue) {
            this.red = red;
            this.green = green;
            this.blue = blue;
        }

        public int getRed() {
            return red;
        }
        public int getGreen() {
            return green;
        }
        public int getBlue() {
            return blue;
        }
        
        public void setRed(int red) {
            this.red = red;
        }
        public void setGreen(int green) {
            this.green = green;
        }
        public void setBlue(int blue) {
            this.blue = blue;
        }

        @Override
        public String toString() {
            return "Color(" + red + ", " + green + ", " + blue + ")";
        }
    }

    public static void main(String[] args) {
   
        Color color1 = new Color(255, 0, 0); 
        Color color2 = new Color(0, 255, 0);
        Color color3 = new Color(0, 0, 255);
        
        System.out.println("color1: " + color1);
        System.out.println("color2: " + color2);
        System.out.println("color3: " + color3);
    }
}





/*
home task 2
import java.util.Scanner;

public class lab2MuhammadTalha {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter the number of strings you want to input:");
        int n = scanner.nextInt();
        scanner.nextLine(); 

        for (int i = 0; i < n; i++) {
            System.out.println("Enter string " + (i + 1) + ":");
            String userInput = scanner.nextLine();
            int hashCode = userInput.hashCode();
            System.out.println("Hash code of \"" + userInput + "\": " + hashCode);
        }

        scanner.close();
    }
}






/*
home task 1
import java.util.Vector;
import java.util.Collections;
import java.util.Scanner;

public class lab2MuhammadTalha {
    public static void main(String[] args) {
        Vector<Integer> numbers = new Vector<>();
        Scanner scanner = new Scanner(System.in);
        
        System.out.println("MuhammadTalha, Enter 5 integers (press Enter after each):");
        for (int i = 0; i < 5; i++) {
            int number = scanner.nextInt();
            numbers.add(number);
        }
        
        Collections.sort(numbers);
        
        System.out.println("Sorted Vector: " + numbers);
        
        int largest = numbers.lastElement(); 
        System.out.println("Largest number: " + largest);
        
        int smallest = numbers.firstElement(); 
        System.out.println("Smallest number: " + smallest);
        
        scanner.close(); 
    }
}





/*
Task 6
import java.util.ArrayList;

public class lab2MuhammadTalha {
    public static void main(String[] args) {
        ArrayList<Integer> list1 = new ArrayList<>();
        list1.add(1);
        list1.add(2);
        list1.add(3);
        list1.add(4);

        ArrayList<Integer> list2 = new ArrayList<>();
        list2.add(5);
        list2.add(6);
        list2.add(7);
        list2.add(8);

        ArrayList<Integer> mergedList = new ArrayList<>(list1);
        mergedList.addAll(list2);

        System.out.println("Merged ArrayList: " + mergedList);
    }
}





/*
task 5
import java.util.ArrayList;
import java.util.Collections;

public class lab2MuhammadTalha {
    public static void main(String[] args) {
        ArrayList<Integer> numbers = new ArrayList<>();
        numbers.add(3);
        numbers.add(1);
        numbers.add(7);
        numbers.add(5);
        numbers.add(9);
        numbers.add(2);
        
        Collections.sort(numbers);
        
        int k = 6; 

        if (k > 0 && k <= numbers.size()) {
            int kthSmallest = numbers.get(k - 1);
            System.out.println("The " + k + "-th smallest element is: " + kthSmallest);
        } else {
            System.out.println("Invalid value of k.");
        }
    }
}







/*
Task 4
import java.util.Vector;

public class lab2MuhammadTalha {
    public static void main(String[] args) {
        Vector<Integer> numbers = new Vector<>();

        for (int i = 1; i <= 10; i++) {
            numbers.add(i);
        }

        System.out.println("The integers in the Vector are:");
        for (int num : numbers) {
            System.out.print(num + " ");
        }

        int sum = 0;
        for (int num : numbers) {
            sum += num;
        }
        System.out.println("\nSum of the integers in the Vector: " + sum);

        int max = numbers.get(0); 
        for (int num : numbers) {
            if (num > max) {
                max = num;
            }
        }
        System.out.println("Maximum element in the Vector: " + max);
    }
}





/*
Task 3

import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;

class Employee implements Comparable<Employee> {
    private int empId;
    private String empName;
    private String empGender;
    private int yearOfJoining;
    private double salary; 

    public Employee(int empId, String empName, String empGender, int yearOfJoining, double salary) {
        this.empId = empId;
        this.empName = empName;
        this.empGender = empGender;
        this.yearOfJoining = yearOfJoining;
        this.salary = salary;
    }

    public int getEmpId() { return empId; }
    public String getEmpName() { return empName; }
    public String getEmpGender() { return empGender; }
    public int getYearOfJoining() { return yearOfJoining; }
    public double getSalary() { return salary; }

    @Override
    public String toString() {
        return "Employee [ID=" + empId + ", Name=" + empName + ", Gender=" + empGender +
               ", Year of Joining=" + yearOfJoining + ", Salary=" + salary + "]";
    }

    @Override
    public int compareTo(Employee other) {
        return Integer.compare(this.yearOfJoining, other.yearOfJoining);
    }
}

class NameComparator implements Comparator<Employee> {
    @Override
    public int compare(Employee e1, Employee e2) {
        return e1.getEmpName().compareTo(e2.getEmpName());
    }
}

public class lab2MuhammadTalha {
    public static void main(String[] args) {
        ArrayList<Employee> employees = new ArrayList<>();

        employees.add(new Employee(319, "Muhammad Jawad", "Male", 2017, 62000.0));
        employees.add(new Employee(320, "Muhammad Ahmed", "Male", 2021, 48000.0));
        employees.add(new Employee(318, "Muhammad Talha", "Male", 2015, 82000.0));
        // Sort by Year of Joining using Comparable (natural ordering)
        Collections.sort(employees);
        System.out.println("Employees sorted by Year of Joining (using Comparable):");
        for (Employee emp : employees) {
            System.out.println(emp);
        }

        employees.sort(new Comparator<Employee>() {
            @Override
            public int compare(Employee e1, Employee e2) {
                return Integer.compare(e1.getYearOfJoining(), e2.getYearOfJoining());
            }
        });

        System.out.println("\nEmployees sorted by Year of Joining (using Comparator):");
        for (Employee emp : employees) {
            System.out.println(emp);
        }
    }
}





/*Task 2
import java.util.ArrayList;
import java.util.Scanner;
public class lab2MuhammadTalha {
    public static void main(String[] args) {
        ArrayList<String> strings = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);

        strings.add("Burger");
        strings.add("Pizza");
        strings.add("Fried Chicken");

        while (true) {
            System.out.println("Menu according to Talha:");
            System.out.println("1. Display the Menu");
            System.out.println("2. Display the largest string");
            System.out.println("3. Exit");
            System.out.print("Muhammad Talha, Enter your choice : ");
            int choice = scanner.nextInt();
            scanner.nextLine(); 

            if (choice == 1) {
                System.out.println("Menu: " + strings);
            } else if (choice == 2) {
                if (!strings.isEmpty()) {
                    String largest = "";
                    for (String str : strings) {
                        if (str.length() > largest.length()) {
                            largest = str;
                        }
                    }
                    System.out.println("Largest string: " + largest);
                } else {
                    System.out.println("The list is empty.");
                }
            } else if (choice == 3) {
                System.out.println("Exiting program.");
                break;
            } else {
                System.out.println("Invalid choice. Try again.");
            }
        }
        scanner.close();
    }
}




Task 1
/*   
    public static void main(String[] args) {
     
        Vector<Integer> numbers = new Vector<>();
        
        for (int i = 1; i <= 10; i++) {
            numbers.add(i);  
        }
        
        System.out.println("The integers in the Vector are:");
        for (int num : numbers) {
            System.out.print(num + " ");
        }
        
        int sum = 0;
        for (int num : numbers) {
            sum += num;
        }
        
        System.out.println("\nSum of the integers in the Vector: " + sum);
    }
}

*/
