
# Getting Started with Swagger Petstore - OpenAPI 3.0

## Introduction

This is a sample Pet Store Server based on the OpenAPI 3.0 specification.  You can find out more about
Swagger at [https://swagger.io](https://swagger.io). In the third iteration of the pet store, we've switched to the design first approach!
You can now help us improve the API whether it's by making changes to the definition itself or to the code.
That way, with time, we can improve the API in general, and expose some of the new features in OAS3.

Some useful links:

- [The Pet Store repository](https://github.com/swagger-api/swagger-petstore)
- [The source API definition for the Pet Store](https://github.com/swagger-api/swagger-petstore/blob/master/src/main/resources/openapi.yaml)

Find out more about Swagger: [https://swagger.io](https://swagger.io)

## Building

### Requirements

The SDK relies on **Node.js** and **npm** (to resolve dependencies). It also requires **Typescript version >=4.1**. You can download and install Node.js and [npm](https://www.npmjs.com/) from [the official Node.js website](https://nodejs.org/en/download/).

> **NOTE:** npm is installed by default when Node.js is installed.

### Verify Successful Installation

Run the following commands in the command prompt or shell of your choice to check if Node.js and npm are successfully installed:

* Node.js: `node --version`

* npm: `npm --version`

![Version Check](https://apidocs.io/illustration/typescript?workspaceFolder=SwaggerPetstoreOpenAPI30&step=versionCheck)

### Install Dependencies

- To resolve all dependencies, go to the **SDK root directory** and run the following command with npm:

```bash
npm install
```

- This will install all dependencies in the **node_modules** folder.

![Resolve Dependencies](https://apidocs.io/illustration/typescript?workspaceFolder=SwaggerPetstoreOpenAPI30&workspaceName=swagger-petstore-openapi-3-0-lib&step=resolveDependency)

## Installation

The following section explains how to use the generated library in a new project.

### 1. Initialize the Node Project

- Open an IDE/text editor for JavaScript like Visual Studio Code. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.

- Click on **File** and select **Open Folder**. Select an empty folder of your project, the folder will become visible in the sidebar on the left.

![Open Folder](https://apidocs.io/illustration/typescript?step=openProject)

- To initialize the Node project, click on **Terminal** and select **New Terminal**. Execute the following command in the terminal:

```bash
npm init --y
```

![Initialize the Node Project](https://apidocs.io/illustration/typescript?step=initializeProject)

### 2. Add Dependencies to the Client Library

- The created project manages its dependencies using its `package.json` file. In order to add a dependency on the *Swagger Petstore - OpenAPI 3.0Lib* client library, double click on the `package.json` file in the bar on the left and add the dependency to the package in it.

![Add SwaggerPetstoreOpenapi30Lib Dependency](https://apidocs.io/illustration/typescript?workspaceFolder=SwaggerPetstoreOpenAPI30&workspaceName=swagger-petstore-openapi-3-0-lib&step=importDependency)

- To install the package in the project, run the following command in the terminal:

```bash
npm install
```

![Install SwaggerPetstoreOpenapi30Lib Dependency](https://apidocs.io/illustration/typescript?step=installDependency)

## Test the SDK

To validate the functionality of this SDK, you can execute all tests located in the `test` directory. This SDK utilizes `Jest` as both the testing framework and test runner.

To run the tests, navigate to the root directory of the SDK and execute the following command:

```bash
npm run test
```

Or you can also run tests with coverage report:

```bash
npm run test:coverage
```

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/sohail2721/tsRepo/tree/2.3.2/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | `Environment` | The API environment. <br> **Default: `Environment.Production`** |
| timeout | `number` | Timeout for API calls.<br>*Default*: `0` |
| httpClientOptions | [`Partial<HttpClientOptions>`](https://www.github.com/sohail2721/tsRepo/tree/2.3.2/doc/http-client-options.md) | Stable configurable http client options. |
| unstableHttpClientOptions | `any` | Unstable configurable http client options. |
| petstoreAuthCredentials | [`PetstoreAuthCredentials`](https://www.github.com/sohail2721/tsRepo/tree/2.3.2/doc/auth/oauth-2-implicit-grant.md) | The credential object for petstoreAuth |
| apiKeyCredentials | [`ApiKeyCredentials`](https://www.github.com/sohail2721/tsRepo/tree/2.3.2/doc/auth/custom-header-signature.md) | The credential object for apiKey |

The API client can be initialized as follows:

```ts
import {
  Client,
  Environment,
  OAuthScopePetstoreAuthEnum,
} from 'swagger-petstore-openapi-3-0-lib';

const client = new Client({
  petstoreAuthCredentials: {
    oAuthClientId: 'OAuthClientId',
    oAuthRedirectUri: 'OAuthRedirectUri',
    oAuthScopes: [
      OAuthScopePetstoreAuthEnum.Writepets,
      OAuthScopePetstoreAuthEnum.Readpets
    ]
  },
  apiKeyCredentials: {
    'api_key': 'api_key'
  },
  timeout: 0,
  environment: Environment.Production,
});
```

## Authorization

This API uses the following authentication schemes.

* [`petstore_auth (OAuth 2 Implicit Grant)`](https://www.github.com/sohail2721/tsRepo/tree/2.3.2/doc/auth/oauth-2-implicit-grant.md)
* [`api_key (Custom Header Signature)`](https://www.github.com/sohail2721/tsRepo/tree/2.3.2/doc/auth/custom-header-signature.md)

## List of APIs

* [Pet](https://www.github.com/sohail2721/tsRepo/tree/2.3.2/doc/controllers/pet.md)
* [Store](https://www.github.com/sohail2721/tsRepo/tree/2.3.2/doc/controllers/store.md)
* [User](https://www.github.com/sohail2721/tsRepo/tree/2.3.2/doc/controllers/user.md)

## SDK Infrastructure

### Configuration

* [HttpClientOptions](https://www.github.com/sohail2721/tsRepo/tree/2.3.2/doc/http-client-options.md)
* [RetryConfiguration](https://www.github.com/sohail2721/tsRepo/tree/2.3.2/doc/retry-configuration.md)
* [ProxySettings](https://www.github.com/sohail2721/tsRepo/tree/2.3.2/doc/proxy-settings.md)

### HTTP

* [HttpRequest](https://www.github.com/sohail2721/tsRepo/tree/2.3.2/doc/http-request.md)

### Utilities

* [ApiResponse](https://www.github.com/sohail2721/tsRepo/tree/2.3.2/doc/api-response.md)
* [ApiError](https://www.github.com/sohail2721/tsRepo/tree/2.3.2/doc/api-error.md)

