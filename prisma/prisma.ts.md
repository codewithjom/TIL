# Prisma Client

```sh
npm install @prisma/client
```

If prisma not yet installed:

```sh
npm install prisma
npx prisma init
```

After creating models:

```sh
npx prisma migrate dev
```

Prefer to create a file `prisma.ts`:

```ts
import { PrismaClient } from "@prisma/client";

let prisma: PrismaClient;
declare global {
  namespace NodeJS {
    interface Global {
      prisma?: PrismaClient;
    }
  }
}

const globalForPrisma = global as typeof globalThis & { prisma?: PrismaClient };

if (process.env.NODE_ENV === "production") {
  prisma = new PrismaClient();
} else {
  if (!globalForPrisma.prisma) {
    globalForPrisma.prisma = new PrismaClient();
  }
  prisma = globalForPrisma.prisma;
}

export default prisma;
```
