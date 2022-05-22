# PayslipGenerator
solution consits of C# consoleapplicaiton (PayslipGenerator) and Xunit test project (PayslipGenerator.Tests)
## Usage Instructions
 run console application:
 
 run Tests

 Applicaiton is written using Microsoft Visual Studio Professional 2022 
 
 ## PayslipGenerator (Console application struture)
 
  **Core** 
  
     Exceptions - Contains custom exception/exceptions where you can use it in the application.
                      
     Interfaces - Contains Interfaces for services used in the application.
     
     Models   - Contains models/entities used in the application.
     
     Services - Contains services for Employee creation and TaxCalculations.
     
  **Infrastructure** 
      Contains source for TaxRules. 
    
 ## PayslipGenerator.Tests (xunit test project)
       xunit test project created test TaxCreation and EmployeeCreation services mainly.possible of extending by adding more unit tests when application grows.  
