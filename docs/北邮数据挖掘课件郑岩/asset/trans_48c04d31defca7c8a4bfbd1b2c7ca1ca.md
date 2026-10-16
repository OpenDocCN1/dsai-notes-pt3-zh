
## ETL Process—Data Cleansing

The data warehouse must store “quality data”—data that is consistent, generally accepted or verified as valuable, and conforms to metadata definitions. The cleansing function can detect data that violates the rules; once detected, such data is either discarded or converted into “clean” data that conforms to the rules, and then loaded into the data warehouse.

If data from operational data sources contains unclean components and non-standard formats, it will cause many problems and troubles for the establishment and maintenance of the data warehouse, especially for the use of Online Analytical Processing (OLAP). These must be resolved during the ETL process, typically including the following methods:

- a. Design spell checking, classification, and cross-checking against standard value tables
- b. Handle names and addresses
- c. Build auxiliary tables or online dictionaries for names and addresses, and use them for verification and correction
- d. Data conversion functions and subroutine libraries

- “Dirty” Data
  - Data does not conform to consistency
  - Use database design tools to define Checks, Validation Criteria, Integrity Constraints
  - Database designers are not very clear about DBMS
  - Constraints have been removed because they degrade operational performance
  - Use certain special codes, flags, or dummy values
  - Multiple target fields—a field depends on other fields, but inconsistently
  - ……

- Cleansing “dirty” data includes three levels:
  - Data cleansing at the data source and application layer (difficult to implement)
  - Data cleansing at the integration and transformation layer
    - Elementization—parsing into atomic data
    - Standardizing the representation of each element value
    - Verifying whether the standardized element values meet consistency requirements
  - Data cleansing within the data warehouse

Usually, the above three approaches are used in combination to achieve high efficiency.

- Principles to ensure smooth data cleansing
  - First, analyze and systematically design the data cleansing process.
  - Second, design a series of data reference tables and data cleansing program libraries based on the main problems and characteristics of the data.
  - The effective combination of the two can address ever-changing and diverse data cleansing problems.

- The data cleansing process
  - Preprocessing: Pre-diagnose and inspect large data load files (especially new files and data sets) rather than loading them blind. Sometimes it is necessary to write a small diagnostic program on the fly, called a “puppy,” which sniffs this huge object (the unknown file) for a hygiene check.
  - Standardization: Apply standard dictionaries built inside the data warehouse to standardize region names, person names, company names, product names, and category names.
  - Duplicate checking: Use various data query methods to avoid introducing duplicate data.
  - Error handling and correction: Write erroneous records and data to log files for further processing.

## ETL Process—Data Loading

- Use loading tools or data query language (SQL)
  - Efficiency issues
  - Avoid violating constraint relationships; pay attention to the loading order

Although the transformation work is rather tedious, it is the simplest of the three steps.

Many ETL tools provide powerful transformation functions. For example, DTS includes: copy field transformation, lowercase string transformation, uppercase string transformation, mid-string transformation, trim string transformation, date-time string transformation, read file transformation, write file transformation, and ActiveX script transformation.

Among these transformation operations, the most commonly used is ActiveX script transformation, because it allows you to write VBScript or JScript yourself to convert data in the source fields into data in the target fields.

In fact, if none of the aforementioned transformations can meet the requirements, ActiveX script transformation is the final choice.

### 2.2.5 ETL Framework

![](img/97ec20d772baf04740a42252ab8f47d8_170_0.png)

DW Populating subsystem reference architecture
Scott Howard (IBM)

### 2.2.6 Composition of ETL

![](img/97ec20d772baf04740a42252ab8f47d8_171_0.png)

### 2.2.7 Related Technologies of ETL

- DTS (Microsoft SQL Server)
- Logically, there are three strategies for implementing the ETL process
  - Remote Extraction
  - Push
  - Pull
- Parallelism
- Data Bulk Load

### ETL Technology—DTS

SQL Server’s Data Transformation Services (abbreviated as DTS) provides a set of OLE DB-based COM objects. Using VBScript, PerlScript, or Microsoft JScript scripting languages to create data transformation programs, it can implement data transformation operations between different OLE DB data sources.

### 2.2.8 ETL Implementation Methods

- Remote Extraction
  - The ETL process is performed on an independent remote platform.
  - It is minimally affected by the existing systems of data sources or the structure of the target warehouse.
  - It hardly affects the CPU and capacity of the source and target systems.
  - It may increase costs; it has high requirements on network bandwidth.

- “Push”
  - The ETL process is carried out in the existing system environment.
  - This method is often used when the existing systems have ample capacity and will not exceed the CPU processing limit.
  - This approach is often used when the existing systems are homogeneous.

- “Pull” (Collocation)
  - The ETL process is carried out at the “warehouse” end.
  - It is often adopted when the existing systems are heterogeneous.
  - It can offer certain advantages when the “warehouse” platform has the required performance and capacity.
  - Since the “warehouse” continues to grow, a long-term strategy may need to be developed.

- (1) High-speed loading: in memory; communicate through the local file system; limited input/output requests
- (2) Bandwidth preservation: avoids accessing the network, so other network-dependent applications are unaffected.

- Parallelism
  - Multithreaded server-side software
  - Multiprocessors (SMP)
- Data Bulk Load
  - “Bulk” is the fastest data loading method.
  - There is a bulk loader in the database; ETL also supports this feature.
  - Avoid using “Insert” or “Update” operations and avoid using ODBC.

### 2.2.9 ETL Tools

- Tools that assist in developing the ETL process are called ETL or ETLM tools. They can standardize ETL process development and make the running and ongoing maintenance processes more efficient.
- Design Studio (Sagent)
- Decision Stream (Cognos)
- ……

### 2.2.10 ETL Applications

For example: “Unified Customer Profile Accumulation Subsystem” (UCIS-etl)

- Framework of UCIS-etl
- Implementation tool — Sagent
- Problems and solutions

### Position of UCIS-ETL in the Unified Customer Profile System

Interface / Service

- Business interface
- Billing interface
- Payment interface
- Other interfaces

Middleware platform (TUXEDO)

Unified Customer Profile Information Model / Database

- Basic profile
- Subscription data
- Billing data
- Other data

Customer Profile Accumulation Subsystem (UCIS-etl)

- 165
- 193
- GSM

User data of existing specialized billing systems

### UCIS-etl Framework—System Function Diagram

Unified Customer Profile

ETL Process

- Generation of customer identifiers and loading of customer profiles
- Conflict detection for basic customer profiles
- Data cleansing, extraction, and transformation
- Formulation of data cleansing, extraction, and transformation rules
- System management
  - Resolving conflicts in basic customer profiles
  - Configuring the mapping between old and new information codes

- 165
- 193
- GSM

User data of existing specialized billing systems

### UCIS-etl Framework—ETL Activity Diagram

ETL Process Activity Diagram

- Extract, Transform & Cleanse
- Staging Area
- Transform, Cleanse & Load
- Formulate rules for data cleansing, extraction, and transformation
- Rule library for cleansing, extraction, and transformation
- Data cleansing, extraction, and transformation
- Specialized databases
- 165
- 193
- GSM
- Intermediate database of the accumulation system
- Conflict database of basic customer profiles in the accumulation system
- Detect whether basic customer profiles conflict
  - Yes
  - No
- Generation of customer identifiers and loading of customer profiles
- Unified customer profile repository

### UCIS-etl Implementation Tool—Sagent

- Data Source DBs
- Data Target DBs
- Sagent Data Access/ Load Server
- Data Flow Service
- Sagent Admin
- Sagent Repository (Oracle, SQL Server...)
- Sagent Design Studio
- System diagram of Sagent ETL series tools
