# Changelog

### 2017-12-12 v1.3.0
* Regenerate generic models against new default SFDC dev org
* ModelGenerator: HTML escape field labels in case of reserved characters, e.g. "&";
* ModelGenerator: add exception to ignore ContentBody non-queryable, non-serializable type in reference fields
* Add basic test for SOQL nested subqueries

### 2017-12-11 v1.2.3
* Fixed incorrect type mapping in ModelGenerator: SFDC "Date" now creates nullable DateTime? model object properties - was previously creating string properties.

### 2017-10-27 v1.2.2
* Added **QuerySingle<T>** convenience method when only a single record is expected from a SOQL query. Will throw an exception if multiple records are returned, to avoid risk of ignoring unknown query results.
* Added additional mocked and functional query tests

### 2017-10-27 v1.2.1
* Enabled XML Documentation/Intellisense support in build output

### 2017-10-25 v1.2.0
* ModelGenerator: Fixed ability to generate all objects at once, and clarified option in console prompts - specifying "all" as the object name will include all available objects in the output.
* Client: Update default client SFDC API version to v41.0
* Models: Regenerated sample models againt SFDC API v41.0
* Update SFDC API references in test cases and documentation to v41.0

### 2017-10-11 v1.1.0
* Update ModelGenerator from netcoreapp1.0 to netcoreapp1.1, fixes crash with 1.0 runtime on MacOS 10.13

### 2017-08-30 v1.0.0
* Initial release

### 2017-07-11 v0.5.1-Beta
* Rebuild to troubleshoot NuGet issue, no code changes 

### 2017-07-11 v0.5.0-Beta
* Fixed issue with processing large query results - client was incorrectly processing the NextRecordsUrl 

### 2017-06-16 v0.4.0-Beta
Updates to Model Generator CLI tool
* No longer removing "__c" suffix from custom object names and field names
* Properly merge config file options with command line arguments when both are supplied

### 2017-06-05 v0.3.0-Beta
Updates to Model Generator CLI tool - existing config scheme was unfriendly, esp. when getting the package from NuGet.
* Local json file for config info is now optional.
* Added interactive prompt to ask for required options when not supplied in args or config file.
* Updated config file model to include additional paramters & options
* Added options to load and save config files based on provided parameters.

### 2017-05-15 v0.2.0-Beta
* Fixed SOSL search methods to return **SearchResult** types. Split into **Search** and **Search\<T\>**:
    * **Search** Generic SOSL search, returns **SearchResult\<SObjectGeneric\>** for when no RETURNING type is specified
    * **Search\<T\>** SOSL search with a RETURNING clause to deserialize the results to a specific type - **SearchResult\<T\>**
* *Breaking Change:* Moved the **SFTypeConverter** utility class and the **FieldType** enum into the ModelGenerator assembly. Neither are comprehensive enough for production use, but are needed for code generation.
* Misc. internal cleanup

### 2017-05-03 v0.1.0-Beta1
* Initial public beta, out of private alpha