# SAI Backend Master

## Overview
SAI Backend Master is a backend application designed to simplify and manage inventory operations, process workflows, and transactional data. Built with scalability, security, and maintainability in mind, it ensures seamless integration and efficient backend management for modern applications.

This application provides:
- Secure authentication and session management using JWT.
- Modular APIs for inventory, process, and transactional management.
- Flexible configuration via `application.properties`.
- Comprehensive documentation using Swagger.

---

## Technologies Used
- **Java**: Core development language.
- **Spring Boot**: Framework for rapid development and scalability.
- **Maven**: Dependency management and build tool.
- **JWT**: Token-based secure authentication.
- **MySQL**: Relational database for persistent storage.
- **Swagger**: API documentation and testing interface.

---

## Features
1. **Authentication and Authorization**:
   - Secure login with JWT token issuance.
   - Password encryption.
2. **Inventory Management**:
   - Create, read, update, and delete inventory items.
3. **Process Management**:
   - Monitor workflows and manage their statuses.
4. **Dynamic Configuration**:
   - Manage application-wide settings via APIs.
5. **Transactional Data Handling**:
   - Maintain records of financial and operational transactions.

---

## Application Configuration

The application is configured through the `application.properties` file. Below are the key configurations and their explanations:

### **Database Configuration**
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/sai_backend
spring.datasource.username=root
spring.datasource.password=root123
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
```
- **`spring.datasource.url`**: The JDBC URL pointing to the MySQL database instance.
- **`spring.datasource.username`**: The username to connect to the database.
- **`spring.datasource.password`**: The password for the database connection.
- **`spring.datasource.driver-class-name`**: Specifies the database driver.

### **Server Configuration**
```properties
server.port=8080
```
- **`server.port`**: Specifies the port on which the application runs.

### **JWT Configuration**
```properties
jwt.secretkey=your_jwt_secret_key
jwt.token.validity=86400000
```
- **`jwt.secretkey`**: The secret key used for signing JWT tokens.
- **`jwt.token.validity`**: The validity period of a JWT token in milliseconds (24 hours in this case).

### **JPA Configuration**
```properties
spring.jpa.hibernate.ddl-auto=update
```
- **`spring.jpa.hibernate.ddl-auto`**: Specifies how Hibernate should handle schema updates (e.g., create, update).

### **Swagger Configuration**
```properties
springdoc.swagger-ui.path=/swagger-ui.html
```
- **`springdoc.swagger-ui.path`**: The URL path to access the Swagger UI for API documentation.

---

## POM.xml Explanation

The `pom.xml` file is a Maven configuration file used to manage project dependencies, plugins, and build settings. Below are key aspects:

### Key Dependencies
1. **Spring Boot Starter**: Provides core Spring Boot functionalities.
2. **Spring Boot Starter Web**: Enables building RESTful web services.
3. **Spring Boot Starter Data JPA**: Simplifies database access with JPA and Hibernate.
4. **MySQL Driver**: Connects the application to a MySQL database.
5. **Spring Security**: Ensures secure access and user authentication.
6. **JWT (Json Web Token)**: Implements token-based authentication.
7. **Swagger Documentation**: Provides API documentation and testing tools.

### Plugins
1. **Spring Boot Maven Plugin**: Used for packaging and running the Spring Boot application.

---

## Controllers

### **GeneralParamsController**
## **POST Endpoints**

### **1. POST /genparam/saveUsageCategories**
Saves usage category details into the database.

### **2. POST /genparam/saveSubCategories**
Adds a new subcategory for items or inventory classification.

### **3. POST /genparam/saveSize**
Stores size-related metadata for items.

### **4. POST /genparam/saveItemType**
Saves a new item type for categorization purposes.

### **5. POST /genparam/saveItemName**
Adds a new item name to the system.

### **6. POST /genparam/saveDiscipline**
Stores discipline-specific metadata for categorization.

### **7. POST /genparam/saveColor**
Adds color information to the system for item tracking.

### **8. POST /genparam/saveCategories**
Saves category information for item organization.

### **9. POST /genparam/saveBrand**
Adds brand details to the inventory metadata.

### **10. POST /genparam/getAllSubCategoriesByDtls**
Retrieves all subcategories based on specific details.

### **11. POST /genparam/getAllItemTypeByDtls**
Fetches item types matching specific details.

### **12. POST /genparam/getAllItemNamesByDtls**
Retrieves item names based on specific criteria.

### **13. POST /genparam/getAllDisciplineByDtls**
Fetches disciplines based on specific metadata.

## **GET Endpoints**

### **1. GET /genparam/getAllUserType**
Retrieves all user types for categorization.

### **2. GET /genparam/getAllUsageCategories**
Fetches all usage categories in the system.

### **3. GET /genparam/getAllSubCategories**
Retrieves all subcategories.

### **4. GET /genparam/getAllSizes**
Gets all item sizes stored in the system.

### **5. GET /genparam/getAllItemType**
Retrieves all item types.

### **6. GET /genparam/getAllItemNames**
Fetches all item names.

### **7. GET /genparam/getAllDiscipline**
Retrieves all disciplines for categorization.

### **8. GET /genparam/getAllColors**
Fetches all colors available for item classification.

### **9. GET /genparam/getAllCategories**
Retrieves all item categories.

### **10. GET /genparam/getAllBrands**
Fetches all brand-related metadata.

---

### **LoginController**
## **POST Endpoints**

### **1. POST /auth/login**
Authenticates a user and generates a JWT token for access.

---

### **MasterController**
Handles master data management.

## **POST Endpoints**

### **1. POST /master/validateDuplicateItemName**
Validates if an item name already exists in the database to prevent duplication.

### **2. POST /master/updateVendorMaster**
Updates the details of an existing vendor in the system.

### **3. POST /master/updateUserMaster**
Modifies user information such as roles or personal details.

### **4. POST /master/updateUOMMaster**
Updates details of a Unit of Measure (UOM).

### **5. POST /master/updateOrgMaster**
Edits organization-level details such as hierarchy or metadata.

### **6. POST /master/updateLocatorMaster**
Updates locator-specific details for inventory locations.

### **7. POST /master/updateLocationMaster**
Edits information related to specific inventory locations.

### **8. POST /master/updateItemMaster**
Updates metadata or details for items in the inventory.

### **9. POST /master/updateEmpMaster**
Edits employee details such as ID, name, or role.

### **10. POST /master/updateDeptMaster**
Updates departmental information within the system.

### **11. POST /master/saveVendorMaster**
Adds a new vendor to the database.

### **12. POST /master/saveUserMaster**
Creates a new user with associated roles and permissions.

### **13. POST /master/saveUOMMaster**
Saves a new Unit of Measure (UOM).

### **14. POST /master/saveOrgMaster**
Creates a new organization entry in the system.

### **15. POST /master/saveLocatorMaster**
Adds a new locator for inventory tracking.

### **16. POST /master/saveLocationMaster**
Creates a new location entry for inventory purposes.

### **17. POST /master/saveItemMaster**
Adds a new item to the inventory with detailed metadata.

### **18. POST /master/saveEmpMaster**
Saves a new employee record into the system.

### **19. POST /master/saveDeptMaster**
Creates a new department entry.

### **20. POST /master/getVendorMasterById**
Fetches vendor details based on their ID.

### **21. POST /master/getUserMasterById**
Retrieves user information by user ID.

### **22. POST /master/getUOMMasterById**
Gets details of a Unit of Measure by its ID.

### **23. POST /master/getOrgMasterByParentId**
Fetches organization details using its parent organization's ID.

### **24. POST /master/getOrgMasterById**
Retrieves details of an organization by its ID.

### **25. POST /master/getOHQ**
Fetches on-hand quantity details for items.

### **26. POST /master/getLocatorMasterByOrgId**
Gets locator details associated with a specific organization ID.

### **27. POST /master/getLocatorMasterById**
Fetches locator details by its ID.

### **28. POST /master/getLocationMasterByOrgId**
Retrieves location information linked to an organization ID.

### **29. POST /master/getLocationMasterById**
Fetches location details by its ID.

### **30. POST /master/getItemMasterByOrgId**
Gets items associated with a specific organization ID.

### **31. POST /master/getItemMasterByItemCode**
Retrieves item details by their unique item code.

### **32. POST /master/getItemMasterById**
Fetches item information by its ID.

### **33. POST /master/getEmpMasterById**
Retrieves employee details using their ID.

### **34. POST /master/getDeptMasterById**
Fetches department details by their ID.

### **35. POST /master/getAllOHQ**
Retrieves the on-hand quantity for all items in the inventory.

### **36. POST /master/deleteVendorMaster**
Removes a vendor record from the database.

### **37. POST /master/deleteUserMaster**
Deletes a user from the system.

### **38. POST /master/deleteUOMMaster**
Removes a Unit of Measure record.

### **39. POST /master/deleteOrgMaster**
Deletes an organization entry from the system.

### **40. POST /master/deleteLocatorMaster**
Deletes a locator entry from the inventory database.

### **41. POST /master/deleteLocationMaster**
Removes a location record.

### **42. POST /master/deleteItemMaster**
Deletes an item from the inventory.

### **43. POST /master/deleteEmpMaster**
Removes an employee record.

### **44. POST /master/deleteDeptMaster**
Deletes a department entry from the system.

### **45. POST /master/changePassword**
Updates a user's password securely.

## **GET Endpoints**

### **1. GET /master/getVendorMaster**
Retrieves all vendors in the system.

### **2. GET /master/getUserMaster**
Fetches a list of all users in the system.

### **3. GET /master/getUOMMaster**
Gets all Unit of Measure records.

### **4. GET /master/getParentOrgMaster**
Retrieves details of parent organizations.

### **5. GET /master/getOrgMaster**
Fetches a list of all organizations.

### **6. GET /master/getLocatorMaster**
Gets details of all locators in the inventory.

### **7. GET /master/getLocationMaster**
Retrieves a list of all inventory locations.

### **8. GET /master/getItemMaster**
Fetches all items in the inventory.

### **9. GET /master/getEmpMaster**
Retrieves a list of all employees.

### **10. GET /master/getDeptMaster**
Fetches a list of all departments.

---

### **ProcessController**


## **POST Endpoints**

### **1. POST /saveReturnNote**
Saves a return note detailing returned items and reasons.

### **2. POST /saveRejectionNote**
Captures information about rejected items, including reasons and quantities.

### **3. POST /saveOutwardGatePass**
Records details of items leaving the facility, including destination and purpose.

### **4. POST /saveNewInspectionReport**
Captures details of new inspections performed on items or batches.

### **5. POST /saveIssueNote**
Records details of items issued from inventory.

### **6. POST /saveInwardGatePass**
Documents items entering the facility, including sources and verification details.

### **7. POST /saveInspectionReport**
Captures details of periodic or specific inspections.

### **8. POST /saveGRN**
Records goods received, including quantities, condition, and source.

### **9. POST /saveAcceptanceNote**
Documents items accepted after inspection or verification.

### **10. POST /getSubProcessDtls**
Retrieves details of subprocesses associated with a workflow.

### **11. POST /doCorrectionProcess**
Initiates corrections in existing processes.

## **GET Endpoints**

### **1. GET /getAllProcess**
Retrieves a list of all processes in the system.

---

### **TransactionsController**


## **POST Endpoints**

### **1. POST /txns/getTxnSummary**
Provides a summary of transactions for a specific organization or time frame.

### **2. POST /txns/getTxnSummaryForAllOrg**
Generates a summary of transactions across all organizations.

### **3. POST /txns/getTxnDtls**
Fetches detailed information about a specific transaction.

### **4. POST /txns/getStockLedger**
Retrieves historical data of stock movements for inventory tracking.

---
### **Dashboard Controller**

## **POST Endpoints**

### **1. POST /getTotalValueOfAllItem**
Calculates and returns the total value of all items in the inventory. Aggregates the value of items based on their quantity and price.

### **2. POST /getPurchaseSummary**
Provides a summary of all purchase transactions, including total purchase amounts and item details.

### **3. POST /getFNSCategory**
Fetches and categorizes items based on the "FNS" category for specific reporting.

### **4. POST /getDashboardIssueNoteData**
Retrieves issue note data for the dashboard, providing insights into issued items and quantities.

---


   

