1.	Encapsulation is the bundling of data and methods that operate on the data into a single unit, called a class. It hides the internal state of an object from the outside world and only exposes the necessary functionality through well-defined interfaces. 
Create an Employee class having data members' Name, Eid, and Basic_Salary, to calculate the HRA is 20% of Basic Salary and DA is 25% of Basic salary and MA is 300 rupee. implement the following queries:
  a) Display the name and gross salary of an employee whose name starts With 'n'
  b).Display the Eid and gross salary whose Eid is equal to 107.
  c)  Count the total number of employees whose salary more than 20000/-

import java.util.ArrayList;
import java.util.List;

public class Employee {
    private String name;
    private int eid;
    private double basicSalary;

    public Employee(String name, int eid, double basicSalary) {
        this.name = name;
        this.eid = eid;
        this.basicSalary = basicSalary;
    }

    public String getName() {
        return name;
    }

    public int getEid() {
        return eid;
    }

    public double getBasicSalary() {
        return basicSalary;
    }

    public double calculateHRA() {
        return 0.2 * basicSalary;
    }

    public double calculateDA() {
        return 0.25 * basicSalary;
    }

    public double calculateMA() {
        return 300;
    }

    public double calculateGrossSalary() {
        return basicSalary + calculateHRA() + calculateDA() + calculateMA();
    }
    public static void main(String[] args) {
        List<Employee> employees = new ArrayList<>();
        employees.add(new Employee("Shweta", 101, 25000));
        employees.add(new Employee("Nisha", 107, 30000));
        employees.add(new Employee("Ramu", 103, 2800));
        employees.add(new Employee("Nikita", 104, 35000));
        employees.add(new Employee("Sujal", 105, 22000));
        System.out.println("Employees whose name starts with 'n':");
        for (Employee employee : employees) {
            if (employee.getName().toLowerCase().startsWith("n")) {
                System.out.println("Name: " + employee.getName());
                System.out.println("Gross Salary: " + employee.calculateGrossSalary());
                System.out.println();
            }
        }
        System.out.println("Employees with Eid equal to 107:");
        for (Employee employee : employees) {
            if (employee.getEid() == 107) {
                System.out.println("Eid: " + employee.getEid());
                System.out.println("Gross Salary: " + employee.calculateGrossSalary());
                System.out.println();
            }
        }
        int count = 0;
        for (Employee employee : employees) {
            if (employee.getBasicSalary() > 20000) {
                count++;
            }
        }
        System.out.println("Total number of employees with salary more than 20000/-: " + count);
    }
}

