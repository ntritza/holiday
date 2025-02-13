# Destinations
(*destinations*)

## Overview

Endpoints for managing holiday destinations

### Available Operations

* [getDestinations](#getdestinations) - Get Destinations
* [createDestination](#createdestination) - Create a Destination
* [deleteDestinationDestinationsDestinationIdDelete](#deletedestinationdestinationsdestinationiddelete) - Delete Destination
* [getDestinationByIdDestinationsDestinationIdGet](#getdestinationbyiddestinationsdestinationidget) - Get Destination By Id
* [updateDestinationDestinationsDestinationIdPut](#updatedestinationdestinationsdestinationidput) - Update Destination

## getDestinations

Retrieve a list of all holiday destinations in the database, optionally filtered by minimum rating.

### Example Usage

```typescript
import { Holiday } from "holiday-test-sdk";

const holiday = new Holiday();

async function run() {
  const result = await holiday.destinations.getDestinations({});

  // Handle the result
  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { HolidayCore } from "holiday-test-sdk/core.js";
import { destinationsGetDestinations } from "holiday-test-sdk/funcs/destinationsGetDestinations.js";

// Use `HolidayCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const holiday = new HolidayCore();

async function run() {
  const res = await destinationsGetDestinations(holiday, {});

  if (!res.ok) {
    throw res.error;
  }

  const { value: result } = res;

  // Handle the result
  console.log(result);
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetDestinationsRequest](../../models/operations/getdestinationsrequest.md)                                                                                         | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[components.Destination[]](../../models/.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.HTTPValidationError | 422                        | application/json           |
| errors.APIError            | 4XX, 5XX                   | \*/\*                      |

## createDestination

Add a new holiday destination to the database.

### Example Usage

```typescript
import { Holiday } from "holiday-test-sdk";

const holiday = new Holiday();

async function run() {
  const result = await holiday.destinations.createDestination({
    country: "Indonesia",
    description: "Beautiful beaches and vibrant culture.",
    name: "Bali",
    rating: 4.8,
  });

  // Handle the result
  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { HolidayCore } from "holiday-test-sdk/core.js";
import { destinationsCreateDestination } from "holiday-test-sdk/funcs/destinationsCreateDestination.js";

// Use `HolidayCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const holiday = new HolidayCore();

async function run() {
  const res = await destinationsCreateDestination(holiday, {
    country: "Indonesia",
    description: "Beautiful beaches and vibrant culture.",
    name: "Bali",
    rating: 4.8,
  });

  if (!res.ok) {
    throw res.error;
  }

  const { value: result } = res;

  // Handle the result
  console.log(result);
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [components.Destination](../../models/components/destination.md)                                                                                                               | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[components.Destination](../../models/components/destination.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.HTTPValidationError | 422                        | application/json           |
| errors.APIError            | 4XX, 5XX                   | \*/\*                      |

## deleteDestinationDestinationsDestinationIdDelete

Remove a holiday destination from the database by its ID.

### Example Usage

```typescript
import { Holiday } from "holiday-test-sdk";

const holiday = new Holiday();

async function run() {
  await holiday.destinations.deleteDestinationDestinationsDestinationIdDelete({
    destinationId: 0,
  });


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { HolidayCore } from "holiday-test-sdk/core.js";
import { destinationsDeleteDestinationDestinationsDestinationIdDelete } from "holiday-test-sdk/funcs/destinationsDeleteDestinationDestinationsDestinationIdDelete.js";

// Use `HolidayCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const holiday = new HolidayCore();

async function run() {
  const res = await destinationsDeleteDestinationDestinationsDestinationIdDelete(holiday, {
    destinationId: 0,
  });

  if (!res.ok) {
    throw res.error;
  }

  const { value: result } = res;

  
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.DeleteDestinationDestinationsDestinationIdDeleteRequest](../../models/operations/deletedestinationdestinationsdestinationiddeleterequest.md)                       | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<void\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.HTTPValidationError | 422                        | application/json           |
| errors.APIError            | 4XX, 5XX                   | \*/\*                      |

## getDestinationByIdDestinationsDestinationIdGet

Retrieve details of a specific holiday destination by its ID.

### Example Usage

```typescript
import { Holiday } from "holiday-test-sdk";

const holiday = new Holiday();

async function run() {
  const result = await holiday.destinations.getDestinationByIdDestinationsDestinationIdGet({
    destinationId: 0,
  });

  // Handle the result
  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { HolidayCore } from "holiday-test-sdk/core.js";
import { destinationsGetDestinationByIdDestinationsDestinationIdGet } from "holiday-test-sdk/funcs/destinationsGetDestinationByIdDestinationsDestinationIdGet.js";

// Use `HolidayCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const holiday = new HolidayCore();

async function run() {
  const res = await destinationsGetDestinationByIdDestinationsDestinationIdGet(holiday, {
    destinationId: 0,
  });

  if (!res.ok) {
    throw res.error;
  }

  const { value: result } = res;

  // Handle the result
  console.log(result);
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.GetDestinationByIdDestinationsDestinationIdGetRequest](../../models/operations/getdestinationbyiddestinationsdestinationidgetrequest.md)                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[components.Destination](../../models/components/destination.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.HTTPValidationError | 422                        | application/json           |
| errors.APIError            | 4XX, 5XX                   | \*/\*                      |

## updateDestinationDestinationsDestinationIdPut

Update details of a specific holiday destination by its ID.

### Example Usage

```typescript
import { Holiday } from "holiday-test-sdk";

const holiday = new Holiday();

async function run() {
  const result = await holiday.destinations.updateDestinationDestinationsDestinationIdPut({
    destinationId: 1,
    destination: {
      country: "Indonesia",
      description: "Beautiful beaches and vibrant culture.",
      name: "Bali",
      rating: 4.8,
    },
  });

  // Handle the result
  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { HolidayCore } from "holiday-test-sdk/core.js";
import { destinationsUpdateDestinationDestinationsDestinationIdPut } from "holiday-test-sdk/funcs/destinationsUpdateDestinationDestinationsDestinationIdPut.js";

// Use `HolidayCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const holiday = new HolidayCore();

async function run() {
  const res = await destinationsUpdateDestinationDestinationsDestinationIdPut(holiday, {
    destinationId: 1,
    destination: {
      country: "Indonesia",
      description: "Beautiful beaches and vibrant culture.",
      name: "Bali",
      rating: 4.8,
    },
  });

  if (!res.ok) {
    throw res.error;
  }

  const { value: result } = res;

  // Handle the result
  console.log(result);
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [operations.UpdateDestinationDestinationsDestinationIdPutRequest](../../models/operations/updatedestinationdestinationsdestinationidputrequest.md)                             | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[components.Destination](../../models/components/destination.md)\>**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| errors.HTTPValidationError | 422                        | application/json           |
| errors.APIError            | 4XX, 5XX                   | \*/\*                      |