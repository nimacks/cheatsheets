## Moq - CheatSheet 

Moq is a popular & friendly mocking framework for .NET. The API  follows the **arrange-act-assert style** and relies heavily on .NET 3.5 features, such as lambdas and extension methods. 

###Terms

- **Mocked Type** - is a interface/class we intend to test by creating a fake version of. 
eg. 
```c# 
Mock productRepoistory= new Mock<IProductRepository>()
``` 
In this example `IProductRepository` is the mocked Type.
-  **Mock** - is the object that is created when we are given a instance of a mocked type. In the above example our mock is `productRepository`.

#### When to create Mocks?
> 
Mocks are most useful when used to create objects that you might not have access to in the context of a unit test. For example, database access, external services

### Common workflow


#### Arrange
> mock an object / dependency
> 
> setup test conditions
 



#### Act
> Perform test



#### Assert
> Verify the test 

###Commonly Used Methods

- `mock.setup()`: 

This method allows you to define conditions and expected results for the test using our mock object

 
- `mock.verify()` :

This method will determine if the conditions created using `mock.setup` have been met

- `mock.verifyAll()`

This method will determine if a the conditions created using have been met

- `mock.setup` 

[I'm an inline-style link](https://www.google.com)

###Examples

> This test setups the mock object such that when the method Hello is called it returns true.

```c#

	var mock = new Mock<TestClass>();
    mock.Setup(x => x.Hello()).Returns(true);
    Assert.AreEqual(mock.Object.Hello(), true);
			
```