## Moq - CheatSheet 

Moq is a popular & friendly mocking framework for .NET. The API  follows the **arrange-act-assert style** and relies heavily on .NET 3.5 features, such as lambdas and extension methods. 

###Terms

- **Mocked Type** - is a interface/class we intend to test by creating a fake version of. eg. `Mock productRepoistory= new Mock<IProductRepository>()` . In this example `IProductRepository` is the mocked Type and `productRepository` is our mock.
-  **Mock** - is the object that is created when we are given a instance of a mocked type. In the above example our mock is `productRepository`.

### When to create Mocks?
Mocks are most useful when used to create objects that you might not have access to in the context of a unit test. For example, database access, external services

### Common workflow
mock an object ->> setup test conditions ->> verify the test

###Commonly Used Methods

- `mock.setup()`: 

This method allows you to state or define what you expect to happen when we run our test on the mock object

 
- `mock.verify()` :


- `mock.verifyAll()`

[I'm an inline-style link](https://www.google.com)

```c#

        public class When_creating_a_customer
        {
            /*shows the basic arrange, act, assert pattern
            shows the simple verification of a method call*/

            [Test]
            public void the_repository_save_should_be_called()
            {
                //Arrange
                var mockRepository = new Mock<ICustomerRepository>();

                mockRepository.Setup(x => x.Save(It.IsAny<Customer>()));

                var customerService = new CustomerService(mockRepository.Object);

                //Act
                customerService.Create(new CustomerToCreateDto());

                //Assert
                mockRepository.VerifyAll();
            }            
        }
```