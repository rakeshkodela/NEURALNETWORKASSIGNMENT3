# NEURALNETWORKASSIGNMENT3


class Employee:
    """
    Generic Employee class with name, family, salary and department
    """

    # data member to count the number of Employees
    no_of_employees = 0

    def __init__(self, name, family_name, salary, department):
        self.__name = name
        self.__family_name = family_name
        self.salary = salary
        self.__department = department
        Employee.no_of_employees += 1

    @staticmethod
    def average_salary(employees):
        """
        function to average salary
        """
        sum = 0
        for employee in employees:
            sum += employee.salary
        return sum / Employee.no_of_employees


class FulltimeEmployee(Employee):
    """
    Full Time Employee is a sub class of Employee
    """

    def __init__(self, name, family_name, salary, department):
        super().__init__(name, family_name, salary, department)

    def full_time_benefits(self):
        print("Few benefits as full time employee.")


def main():
    employees = []
    fte1 = FulltimeEmployee("Employee1", "FamilyName1", 120000, "Management")
    fte1.full_time_benefits()
    employees.append(fte1)
    fte2 = FulltimeEmployee("Employee2", "FamilyName2", 180000, "RnD")
    employees.append(fte2)
    emp1 = Employee("Employee3", "FamilyName3", 160000, "Marketing")
    employees.append(emp1)
    emp2 = Employee("Employee4", "FamilyName4", 135000, "HR")
    employees.append(emp2)
    print("Average salary:", FulltimeEmployee.average_salary(employees))


if __name__ == "__main__":
    main()
    
    **
 the following output for the above code is shown below:**
 
 Few benefits as full time employee.
Average salary: 148750.0





import numpy as np


def replace_maxmium(array, replace_value, axis):
    """ choose from x or y depending on condition: np.where(condition, x, y) """
    output = np.where(array == np.max(
        array, axis=1).reshape(-1, 1), 0 * array, array)
    print(output)


def main():

    # Using NumPy create random vector of size 20 having only float
    # in the range 1-20.

    # continuous uniform distribution in [0, 1).
    # To sample Unif[a, b): (b - a) * random_sample() + a
    random20 = np.random.random_sample(20) * 20 + 1

    # Reshape the array to 4 by 5
    random20_4by5 = random20.reshape((4, 5))

    # Replace the max in each row by 0(axis=1)
    replace_maxmium(random20_4by5, 0, 1)


if __name__ == "__main__":
    main()
    
    
  **  the following  code produces the output:**
    
    
    [[ 0.         19.13079804  9.07552786  7.55916553 15.20009297]
 [14.34958746  6.22806095 13.80848379 10.5895159   0.        ]
 [ 0.          8.34080178 14.00225284  4.78230927  6.22193229]
 [ 2.1858963   5.53081414  2.13392825  0.          1.65690443]]
​
