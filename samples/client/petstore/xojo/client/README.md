# Xojo API client for OpenAPIClient

This is a sample server Petstore server. For this sample, you can use the api key `special-key` to test the authorization filters.

## Overview
This API client was generated by the [OpenAPI Generator](https://openapi-generator.tech) project.  By using the [openapi-spec](https://github.com/OAI/OpenAPI-Specification) from a remote server, you can easily generate an API client.

- API version: 1.0.0
- Package version: 
- Generator version: 7.15.0-SNAPSHOT
- Build package: org.openapitools.codegen.languages.XojoClientCodegen

## Installation

This project contains generated code suitable for both Desktop and Console applications on all operating systems.

The code is generated for Xojo's API v1.

The generated code is packaged into a single Module (`OpenAPIClient`), which we suggest copying to your project after opening the generated `OpenAPIClient.xojo_project` in [Xojo](https://xojo.com/). Working in the generated Xojo project is not recommended.

> See also Xojo's [Sharing code among multiple projects](https://documentation.xojo.com/topics/code_management/sharing_code_among_multiple_projects.html).

This project depends on [Xoson](https://github.com/Topheee/xoson) `v2.2.0` (and above). Download it to your computer:
```shell
git clone 'https://github.com/Topheee/xoson.git'
```

Open the `Xoson.xojo_project` from the cloned git repository with Xojo and copy the `Xoson` module to your project. Similarly, open the `OpenAPIClient.xojo_project` file with Xojo and copy `OpenAPIClient` to your project.

> Since Xojo currently has no package manager, you need to manually copy both the `Xoson` and the `OpenAPIClient` modules to your Xojo project.

Both modules must not be copied into another module, but must reside at the top level of your project.

### Customization

The generator can be configured with the following options.

Option | Used | Description
--- | --- | ---
`projectName` | `OpenAPIClient` | The name of the generated project and module.
`nonPublicApi` | `false` | Generate `Protected` instead of `Public` methods, if set.
`library` | `httpsocket` | Internal Xojo standard library object to use. Currently only `httpsocket` (`HTTPSocket` class) is supported.
`serializationLibrary` | `{xoson` | Internal library to use for serialization. Currently only `xoson` ([Xoson](https://github.com/Topheee/xoson) library) is supported.
`supportsAsync` | `true` | If `true`, generated APIs will use callbacks instead of blocking the main thread.

### Usage

Communication with the OpenAPI server is done by instantiating one of the classes below `OpenAPIClient.APIs`, configuring it - by setting `BasePath`, `UseHTTPS`, and `Port` - and invoking the `Public ` methods.
The methods always return immediately and the network communication is done in the background. To obtain the results and errors of each request, you need to implement the respective `CallbackHandler` interfaces:

- `OpenAPIClient.APIs.PetApiCallbackHandler`
- `OpenAPIClient.APIs.StoreApiCallbackHandler`
- `OpenAPIClient.APIs.UserApiCallbackHandler`


Create an object of your implementing class and assign it to the `CallbackHandler` property of the API object.

This callback handler has exactly one method definition for each operation. This method is invoked when the operation finishes. It's first parameter `status As OpenAPIClient.OpenAPIClientException` is always set. If `status.IsError` is `False`, the operation succeeded and the return value (either `data` or `file`) - if available - contains valid information.

> The property `AdditionalHeaders` allows sending further headers with each request. Set it to a new `Dictionary`, with the Keys being the header names and the values either being a single String or an array of Strings.

__Error handling__, as well as status reporting, is done via class `OpenAPIClient.OpenAPIClientException`. Note that an instance of this class does not always indicate an error - check `IsError` to find out.
- `ErrorNumber` is set to one of the `OpenAPIClient.kError` constants, or `0` in case of no error.
- `HTTPStatus` is set to the HTTP status code as returned by the server. If the error is unrelated to HTTP, this property is `-1`.
- `SocketCode` contains the socket error, if any; otherwise `0`.

## Documentation for API Endpoints

All URIs are relative to *http://petstore.swagger.io/v2*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*OpenAPIClient.APIs.PetApi* | [**AddPet**](PetApi.md#addpet) | **POST** /pet | Add a new pet to the store
*OpenAPIClient.APIs.PetApi* | [**DeletePet**](PetApi.md#deletepet) | **DELETE** /pet/{petId} | Deletes a pet
*OpenAPIClient.APIs.PetApi* | [**FindPetsByStatus**](PetApi.md#findpetsbystatus) | **GET** /pet/findByStatus | Finds Pets by status
*OpenAPIClient.APIs.PetApi* | [**FindPetsByTags**](PetApi.md#findpetsbytags) | **GET** /pet/findByTags | Finds Pets by tags
*OpenAPIClient.APIs.PetApi* | [**GetPetById**](PetApi.md#getpetbyid) | **GET** /pet/{petId} | Find pet by ID
*OpenAPIClient.APIs.PetApi* | [**UpdatePet**](PetApi.md#updatepet) | **PUT** /pet | Update an existing pet
*OpenAPIClient.APIs.PetApi* | [**UpdatePetWithForm**](PetApi.md#updatepetwithform) | **POST** /pet/{petId} | Updates a pet in the store with form data
*OpenAPIClient.APIs.PetApi* | [**UploadFile**](PetApi.md#uploadfile) | **POST** /pet/{petId}/uploadImage | uploads an image
*OpenAPIClient.APIs.StoreApi* | [**DeleteOrder**](StoreApi.md#deleteorder) | **DELETE** /store/order/{orderId} | Delete purchase order by ID
*OpenAPIClient.APIs.StoreApi* | [**GetInventory**](StoreApi.md#getinventory) | **GET** /store/inventory | Returns pet inventories by status
*OpenAPIClient.APIs.StoreApi* | [**GetOrderById**](StoreApi.md#getorderbyid) | **GET** /store/order/{orderId} | Find purchase order by ID
*OpenAPIClient.APIs.StoreApi* | [**PlaceOrder**](StoreApi.md#placeorder) | **POST** /store/order | Place an order for a pet
*OpenAPIClient.APIs.UserApi* | [**CreateUser**](UserApi.md#createuser) | **POST** /user | Create user
*OpenAPIClient.APIs.UserApi* | [**CreateUsersWithArrayInput**](UserApi.md#createuserswitharrayinput) | **POST** /user/createWithArray | Creates list of users with given input array
*OpenAPIClient.APIs.UserApi* | [**CreateUsersWithListInput**](UserApi.md#createuserswithlistinput) | **POST** /user/createWithList | Creates list of users with given input array
*OpenAPIClient.APIs.UserApi* | [**DeleteUser**](UserApi.md#deleteuser) | **DELETE** /user/{username} | Delete user
*OpenAPIClient.APIs.UserApi* | [**GetUserByName**](UserApi.md#getuserbyname) | **GET** /user/{username} | Get user by user name
*OpenAPIClient.APIs.UserApi* | [**LoginUser**](UserApi.md#loginuser) | **GET** /user/login | Logs user into the system
*OpenAPIClient.APIs.UserApi* | [**LogoutUser**](UserApi.md#logoutuser) | **GET** /user/logout | Logs out current logged in user session
*OpenAPIClient.APIs.UserApi* | [**UpdateUser**](UserApi.md#updateuser) | **PUT** /user/{username} | Updated user


## Documentation For Models

 - [OpenAPIClient.Models.ApiResponse](ApiResponse.md)
 - [OpenAPIClient.Models.Category](Category.md)
 - [OpenAPIClient.Models.Order](Order.md)
 - [OpenAPIClient.Models.Pet](Pet.md)
 - [OpenAPIClient.Models.Tag](Tag.md)
 - [OpenAPIClient.Models.User](User.md)


## Documentation For Authorization


## petstore_auth

- **Type**: OAuth
- **Flow**: implicit
- **Authorization URL**: http://petstore.swagger.io/api/oauth/dialog
- **Scopes**: 
 - **write:pets**: modify pets in your account
 - **read:pets**: read your pets

## api_key

- **Type**: API key
- **API key parameter name**: api_key
- **Location**: HTTP header


## Author



