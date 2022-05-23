# PayslipGenerator
Solution has been implemented as a C# console application to generate a monthly payslip information given employee details name(firstname and lastname) and annual salary as console arguments. Payslip information details Employee's name, Gross monthly income , 
 monthly payslip information contains  name,gross monthly income,monthly income tax and net monthly income. 
 
 Gross monthly income = annual salary /12 
 monthly income tax = income tax calculated according to the tax calculations given below. 
 
 $0 - $20 000 - $0
 
 $20001 -$40000 -10c for each $1 over $20,000
 
 $40,001 - $80,000 - 20c for each $1 over $40,000
 
 $80,001 - $180,000 -30c for each $1 over $80,000
 
 $180,001 and over - 40c for each $1 over $180,000
 

Soltuion consits of C# consoleapplicaiton (PayslipGenerator) and Xunit test project (PayslipGenerator.Tests)
## Usage Instructions
Applicaiton is written using Microsoft Visual Studio Professional 2022 

install/run  PayslipGenerator(console application):

1.)command line:

 Open the folder structure and navigate to the PayslipGenerator class Library folder using command line
 
     1.)dotnet build
     
     2.)dotnet run <arg1> <arg2> 
     arg1- firstname and lastname sepearted by space ("Mary Song")
           
     arg2- Annual Salary (60000)
          
     E.g: dotnet run "Mary Song" 60000
 
 programm will then output the payslip details.

 run Tests:
 
     Navigate to the PayslipGenerator.Tests using command line 
     
     run dotnet test
     
 Alternatively you can open the PayslipGenerator.sln with Visual Studio to run the Console applicaiton providing command line arguments via debug and run the unit tests using test explorer. 
 
 ## PayslipGenerator (Console application struture)
 Core Folder includes 
 
 1.)Models(Entities)
 
 2.)Interfaces
 
 3.)Services
 
 4.)Exceptions
 
 and Infrastructure folder
 
  **Core Folder** 
  
   PayslipCreator.cs - Contains logic responsible for payslip creation. class contructor takes ITaxItemsSource and IEmployeeService as arguments which are being
                         used to generate payslip information.
                         
   Exceptions folder - Contains custom exception/exceptions where you can use it in the application to raise exceptions.
                      
   Interfaces folder - Contains Interfaces for services used in the application. this contracts can be used the mock the behaviour of the services when needed(specially in unit testing).
     
   Models folder  - Contains models/entities used in the application. These are models( or entities) used throught the application.Employee model - firstname, lastname and annualsalary with validation.
                 TaxItem model - minValue and maxValue and TaxRate 
                
 Services folder - Contains services for Employee creation(EmployeeService) and Monthly tax calculation(TaxCalculateService) implementing IEmployeeService and            ITaxCalculateService.
  
      
    
     
  **Infrastructure Folder** 
  
  TaxItemsSource.cs -  This will generate the list of TaxItems as a collection. purpose of this class creation is to seperate the Tax Items generation. 
     
 Design decisions: Folder structue (Core and Infrastrucre and can be extended) created for seprate models(entities),services,exceptions and interfaces used in the applicaitons to make the solution structure simply well-factored. Interfaces are used in appropriate places to swap the implementation logic whenever needed.(E.g: in unit testing). Nature of this structure is to support modularity and encapsulation.
 
 ## PayslipGenerator.Tests (xunit test project)
 
 xunit test project created test TaxCreation and EmployeeCreation services mainly.possibility of extending by adding more unit tests when application logic grows.
 EmployeeServiceCreate.cs - unit tests around Employee creation and exception raising for validating fisrtname , lastname and annual salary.
 TaxCalculatorCalcuate.cs - unit tests around tax creation logic and exception raising. 
 
 These tests were added to cover  Taxcalculationlogic and Employee creation logic which is the main purpose of the Payslip generation. Can have intergration tests convering more bussiness logic.
 
 
 
       
