# AWS Lambda Function Invoke Python example

This folder contains an AWS Lambda Function example in Python on AWS (Amazon Web Services).

It invokes a Lambda function using the Client API (low-level) of Boto 3.

## Requirements

* You must have an [Amazon Web Services (AWS)](http://aws.amazon.com/) account.

* The code was written for Python 3 and AWS SDK for Python (Boto3).

* This example uses Client API (low-level) of Boto 3.

* Install the AWS SDK for Python (Boto3).

  Install the latest Boto 3 release via pip:

  ```bash
  pip install boto3
  ```

## Using the code

* Configure your AWS access keys.

  **Important:** For security, it is strongly recommend that you use IAM users instead of the root account for AWS access.

  When you initialize a new service client without supplying any arguments, the AWS SDK for Java attempts to find AWS credentials by using the default credential provider chain.

  Setting your credentials for use by the AWS SDK for Java can be done in a number of ways, but here are the recommended approaches:

  * The default credential profiles file
  
    Set credentials in the AWS credentials profile file on your local system, located at:

    `~/.aws/credentials` on Linux, macOS, or Unix

    `C:\Users\USERNAME\.aws\credentials` on Windows

    This file should contain lines in the following format:

    ```bash
    [default]
    aws_access_key_id = <your_access_key_id>
    aws_secret_access_key = <your_secret_access_key>
    ```
    Substitute your own AWS credentials values for the values `<your_access_key_id>` and `<your_secret_access_key>`.

  * Environment variables `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY`
  
    Set the `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` environment variables.

    To set these variables on Linux, macOS, or Unix, use `export`:

    ```bash
    export AWS_ACCESS_KEY_ID=<your_access_key_id>
    export AWS_SECRET_ACCESS_KEY=<your_secret_access_key>
    ```

    To set these variables on Windows, use `set`:

    ```bash
    set AWS_ACCESS_KEY_ID=<your_access_key_id>
    set AWS_SECRET_ACCESS_KEY=<your_secret_access_key>
    ```

* Create a Lambda function on AWS.

  You can use the AWS Lambda Function Hello World JSON Java example: [awslambdahellojson](/awslambdahellojson).

* You can select the bucket region changing the value of `REGION` variable in the code.

* You can change the values of the payload to the Lambda function in the code (payload):

```bash
  {
    'first_name': 'Peter',
    'last_name': 'Parker'
  }
  ```

* Run the code.

  You must provide 1 parameter:
  
  * `<FUNCTION_NAME>` = Lambda function name

  Run application:

  ```bash
  python lambdainvoke.py function-name
  ```

  You can use as Lambda function name 2 options:
  
  * Function name
    
    Ex.: `HelloJsonPython`

  * ARN value
  
    Ex.: `arn:aws:lambda:eu-west-1:123456789012:function:HelloJsonPython`
  
    You can retrieve the ARN value by looking at the function in the AWS Console.

* Test the application.

  You should see the response of the Lambda function.

  For example:

  * `Function response payload:`
  * `{'message': 'Hello Peter Parker!'}`