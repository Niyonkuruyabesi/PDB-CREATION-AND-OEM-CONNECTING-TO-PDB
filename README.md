# PDB-CREATION-AND-OEM-CONNECTING-TO-PDB
PDB creating and deleting it , OEM connecting to pdbs

#  Database Creation, Deletion & OEM

###  Course: DATABASE DEVELOPMENT WITH PL/SQL
###  Names: **Niyonkuru Nyirimpeta Yabesi**  
###  Student_id: **27715**

---

##  Overview

This assignment demonstrates practical **Oracle Database Administration** tasks involving **Pluggable Databases (PDBs)** and **Oracle Enterprise Manager Express (OEM)**.

It includes:
1.  Creating a new PDB for class work  
2.  Creating and deleting a temporary PDB  
3.  Configuring and accessing Oracle Enterprise Manager Express (OEM)

---

##  Task 1: Create a New Pluggable Databas

**SQL Command Used:**
```sql
CREATE PLUGGABLE DATABASE plsql_class2025db 
ADMIN USER yabesi_plsqlauca_27715 IDENTIFIED BY Jabezi96
FILE_NAME_CONVERT = (
  'C:\app\niyon\product\21c\oradata\XE\pdbseed', 
  'C:\app\niyon\product\21c\oradata\XE\plsql_class2025db'
);
```

 Task 2: Create and Delete Another PDB

SQL Command (Create):
```sql
CREATE PLUGGABLE DATABASE ya_to_delete_pdb_27715
ADMIN USER yabesi_plsqlauca_27715 IDENTIFIED BY Jabezi96
FILE_NAME_CONVERT = (
  'C:\app\niyon\product\21c\oradata\XE\pdbseed',
  'C:\app\niyon\product\21c\oradata\XE\to_delete_pdb'
);
```

SQL Command (Delete):
```sql
ALTER PLUGGABLE DATABASE ya_to_delete_pdb_27715 CLOSE IMMEDIATE;
DROP PLUGGABLE DATABASE ya_to_delete_pdb_27715 INCLUDING DATAFILES;
```
✅ Result:
The temporary PDB ya_to_delete_pdb_27715 was created and successfully deleted after testing.

 Task 3: Oracle Enterprise Manager (OEM) Configuration

Steps Taken:

Verified current OEM port:
```sql
SELECT DBMS_XDB_CONFIG.GETHTTPSPORT FROM DUAL;
```
Accessed OEM in a browser:

https://localhost:5500/em


Logged in using:

Username: yabesi_plsqlauca_27715

Password: *****

✅ Result:
OEM Express dashboard loaded successfully for plsql_class2025db.
