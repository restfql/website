---
sidebar_position: 1
---

# Express

## Usage

1. install with a package manager
```bash
npm install express-restfql

yarn add express-restfql
```

2. Add the middleware to your express server

```ts
import express from 'express';
import restfql from 'express-restfql';
const app = express();

app.use(restfql)

app.get('/', (req, res) => {
  res.json({
    message: 'Hello World!', 
    description: "awesome description",
    tags:{
        mandatory: ["mand_tag1","mand_tag1"],
        optional:  ["opt_tag1","opt_tag1"],
    }
});
});

app.listen(3000);
```

3. query passing the model as a query param call `fql`
# ![preview query](https://user-images.githubusercontent.com/3071208/224512973-f5ae4679-2790-4a55-86e6-e0da1293c69b.png)
