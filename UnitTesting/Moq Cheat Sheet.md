## Moq - CheatSheet 

Moq is a popular & friendly mocking framework for .NET. The API also follows the arrange-act-assert style and relies heavily on .NET 3.5 features, such as lambdas and extension methods. The learning curve is quite easy, but you need to feel comfortable with using lambdas

###Glossary

- **Mocked Type** - is a class which we intend to test by creating a fake version of it. eg. `Mock productRepoistory= new Mock<IProductRepository>()` . In this example `IProductRepository` is the mocked Type.

###Commonly Used Methods


- `mock.setup()` : 
- `mock.verify()` :

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