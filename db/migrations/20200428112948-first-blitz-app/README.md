# Migration `20200428112948-first-blitz-app`

This migration has been generated by Alex Nielsen at 4/28/2020, 11:29:48 AM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql
PRAGMA foreign_keys=OFF;

CREATE TABLE "quaint"."Project" (
    "id" INTEGER NOT NULL  PRIMARY KEY AUTOINCREMENT,
    "name" TEXT NOT NULL  
) 

CREATE TABLE "quaint"."Task" (
    "id" INTEGER NOT NULL  PRIMARY KEY AUTOINCREMENT,
    "name" TEXT NOT NULL  ,
    "projectId" INTEGER NOT NULL  ,FOREIGN KEY ("projectId") REFERENCES "Project"("id") ON DELETE CASCADE ON UPDATE CASCADE
) 

PRAGMA "quaint".foreign_key_check;

PRAGMA foreign_keys=ON;
```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration ..20200428112948-first-blitz-app
--- datamodel.dml
+++ datamodel.dml
@@ -1,0 +1,26 @@
+datasource sqlite {
+  provider = "sqlite"
+  url      = "file:./db.sqlite"
+}
+
+generator client {
+  provider = "prisma-client-js"
+}
+
+// --------------------------------------
+// model Project {
+// id        Int      @default(autoincrement()) @id
+// name      String
+// }
+model Project {
+  id    Int    @default(autoincrement()) @id
+  name  String
+  tasks Task[]
+}
+
+model Task {
+  id        Int     @default(autoincrement()) @id
+  name      String
+  project   Project @relation(fields: [projectId], references: [id])
+  projectId Int
+}
```

