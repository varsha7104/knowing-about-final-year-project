# 1) Add a postgresql database(Neon) 
a) Open neon website
b)create a project
c)connect database
d)create a .env file  to the root directory and store with 
```
DATABASE_URL="postgresql://neondb_owner:npg_pkA7tlce6TFn@ep-fragrant-dawn-afc8nlzo-pooler.c-2.us-west-2.aws.neon.tech/neondb?sslmode=require&channel_binding=require"

```
# 2) add this 
<img width="806" height="30" alt="image" src="https://github.com/user-attachments/assets/673facf6-aef9-4d46-b74b-7908ca46d14c" />
<img width="400" height="17" alt="image" src="https://github.com/user-attachments/assets/0d6609b8-a988-478a-8511-7216e98d1faf" />
Packages get added 
# 3) add index.ts file
1) create a db folder in src
2) create index.ts file 
3) add this snippet
   ```
   import { drizzle } from "drizzle-orm/neon-http";

   export const db = drizzle(process.env.DATABASE_URL!);

   ```
4)now create a file
schema .ts
```
import { integer, pgTable, varchar } from "drizzle-orm/pg-core";

export const usersTable = pgTable("users", {
  id: integer().primaryKey().generatedAlwaysAsIdentity(),
  name: varchar({ length: 255 }).notNull(),
  age: integer().notNull(),
  email: varchar({ length: 255 }).notNull().unique(),
});


```
5) make a drizzleconfig.ts
   ```
   import 'dotenv/config';
import { defineConfig } from 'drizzle-kit';

 export default defineConfig({
  out: './drizzle',
  schema: './src/db/schema.ts',
  dialect: 'postgresql',
  dbCredentials: {
    url: process.env.DATABASE_URL!,
  },
}); ```
6) write this command 

```
npx drizzle-kit push

```
you will see the changed table in the neon
7) 
add packages in package.json
   ```
   "db:push": "drizzle-kit push",
   "db:studio": "drizzle-kit studio"
   ```
8)open  local drizzle
```
npx drizzle-kit push

```
