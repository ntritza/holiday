<!-- Start SDK Example Usage [usage] -->
```typescript
import { Holiday } from "holiday";

const holiday = new Holiday();

async function run() {
  const result = await holiday.general.readRootGet();

  // Handle the result
  console.log(result);
}

run();

```
<!-- End SDK Example Usage [usage] -->