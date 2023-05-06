## What are superglobals ? 
In PHP, superglobals are special predefined variables that are accessible from anywhere in a script, and are commonly used to pass data between pages or scripts. The superglobal arrays in PHP are as follows:

### $_SERVER
Contains information about the server and execution environment, such as request headers, server software, and request method.

### $_GET
Contains variables passed to the script via the URL parameters, also known as query strings.

### $_POST
Contains variables sent to the script via HTTP POST method, commonly used for form submissions.

### $_FILES
Contains information about uploaded files.
The $_FILES array is an associative array, where the keys represent the name of the file input field in the form and the values are arrays containing various information about the uploaded file, such as its name, type, size, and location on the server. The array has the following structure:
```
$_FILES['input_name'] = array(
  'name' => 'uploaded_file_name.ext',
  'type' => 'file_type',
  'tmp_name' => 'temporary_file_name',
  'error' => 'error_code',
  'size' => 'file_size_in_bytes'
);
```

### $_COOKIE
Contains all cookies that have been sent to the current script via HTTP cookies

### $_SESSION
Contains variables stored on the server-side session.

### $_REQUEST
Contains variables passed to the script via both GET and POST methods.

### $_GLOBALS
Contains all the global variables defined in the current script, including those defined outside of any function or class.

### $_ENV
Contains all the environment variables available to the current script. Environment variables are system variables that are used to store information about the environment in which the script is running, such as the current user, the system path, and various configuration settings.