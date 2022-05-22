# PayslipGenerator
Solution has been implemented as a C# console application to generate a monthly payslip information given employee details firstname,lastname and annual salary as console arguments. Payslip information details Employee's name, Gross monthly income , 
 monthly payslip information contains  name,gross monthly income,monthly income tax and net monthly income. 
 
 Gross monthly income = annual salary /12 
 monthly income tax = income tax calculated according to the tax rules given below. 
 
 $0 - $20 000 - $0
 $20001 -$40000 -10c for each $1 over $20,000
 $40,001 - $80,000 - 20c for each $1 over $40,000
 $80,001 - $180,000 -30c for each $1 over $80,000
 $180,001 and over - 40c for each $1 over $180,000
 

Soltuion consits of C# consoleapplicaiton (PayslipGenerator) and Xunit test project (PayslipGenerator.Tests)
## Usage Instructions
 run console application:
 
 run Tests

 Applicaiton is written using Microsoft Visual Studio Professional 2022 
 
 ## PayslipGenerator (Console application struture)
 
  **Core** 
     PayslipCreator.cs - Contains logic responsible for payslip creation. class contructor takes ITaxItemsSource and IEmployeeService as arguments which are later
                         to generate payslip information.
     Exceptions - Contains custom exception/exceptions where you can use it in the application.
                      
     Interfaces - Contains Interfaces for services used in the application. this contracts can be used the mock the behaviour of the services when needed(specially 
                  in unit testing.
     
     Models   - Contains models/entities used in the application. These are models( or entities) used throught the application. 
                 Employee model - firstname , lastname and annualsalary with validation.
                 TaxItem model - minValue and maxValue and TaxRate defining a tax rule 
                 
     
     Services - Contains services for Employee creation(EmployeeService) and Monthly tax calculation(TaxCalculateService) implementing IEmployeeService and            ITaxCalculateService.
     
  **Infrastructure** 
     TaxItemsSource.cs -  This will generate the list of TaxItems as a collection. purpose of this class creation is to seperate the Tax Items generation. 
    
 ## PayslipGenerator.Tests (xunit test project)
       xunit test project created test TaxCreation and EmployeeCreation services mainly.possible of extending by adding more unit tests when application grows.  
