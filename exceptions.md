### What is an exception?

In PHP, an exception is a way to handle errors or exceptional situations that may arise during the execution of a program. Exceptions provide a structured way to handle errors and allow the program to gracefully recover from them.


### Throwing an exception
To throw an exception in PHP, you can use the throw keyword, followed by an instance of the Exception class or a subclass of Exception. For example:

```
if ($a < 0) {
  throw new Exception("Value of 'a' cannot be negative");
}
```

### Catcing exception
To catch an exception in PHP, you can use a try/catch block. The try block contains the code that may throw an exception, and the catch block contains the code that handles the exception. For example:
```
try {
  // some code that may throw an exception
} catch (Exception $e) {
  // code that handles the exception
  echo "Caught exception: " . $e->getMessage();
}
```

### Custom exceptions
In this example, if an exception is thrown in the try block, the code in the catch block will be executed. The exception object is passed as an argument to the catch block, which can then be used to get information about the exception, such as its message or its stack trace.

You can also define your own exception classes in PHP by extending the Exception class. This allows you to create custom exceptions that are specific to your application and provide more detailed information about the error that occurred. For example:
```
class MyException extends Exception {
  public function __construct($message, $code = 0, Exception $previous = null) {
    parent::__construct($message, $code, $previous);
  }
  
  public function __toString() {
    return __CLASS__ . ": [{$this->code}]: {$this->message}\n";
  }
}
```

In this example, the MyException class extends the Exception class and overrides the constructor and the __toString() method. This allows you to create instances of MyException with custom messages and codes, and to customize how the exception is converted to a string when it is displayed.

### Throwable

The Throwable interface is a built-in PHP interface that defines the basic methods that an object must implement in order to be throwable as an exception or error. It is not possible to implement this interface in a regular class, since it is a core language feature.

Instead, to create a custom exception class, you should extend the built-in Exception class or one of its subclasses, such as RuntimeException, which already implement the Throwable interface. By doing so, your custom exception class will also implement the Throwable interface and can be thrown and caught like any other exception.