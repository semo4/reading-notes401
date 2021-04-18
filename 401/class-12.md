# Spring RESTful Routing & Static Files

![images](https://scotch-res.cloudinary.com/image/upload/w_1050,q_auto:good,f_auto/v1536390809/rtum7myajmkixdwpap8i.png)

- Spring Boot provides a very good support to building RESTful Web Services for enterprise applications.

## Rest Controller
- The @RestController annotation is used to define the RESTful web services. It serves JSON, XML and custom response.

## Request Mapping
- The @RequestMapping annotation is used to define the Request URI to access the REST Endpoints. We can define Request method to consume and produce object. The default request method is GET.
## Request Body
- The @RequestBody annotation is used to define the request body content type.

## Path Variable
- The @PathVariable annotation is used to define the custom or dynamic request URI. The Path variable in request URI is defined as curly braces {}.

## Request Parameter
- The @RequestParam annotation is used to read the request parameters from the Request URL. By default, it is a required parameter.

## GET API
- The default HTTP request method is GET. This method does not require any Request Body. You can send request parameters and path variables to define the custom or dynamic URL.

## POST API
- The HTTP POST request is used to create a resource. This method contains the Request Body. We can send request parameters and path variables to define the custom or dynamic URL.

## PUT API
- The HTTP PUT request is used to update the existing resource. This method contains a Request Body. We can send request parameters and path variables to define the custom or dynamic URL.

## DELETE API
- The HTTP Delete request is used to delete the existing resource. This method does not contain any Request Body. We can send request parameters and path variables to define the custom or dynamic URL.