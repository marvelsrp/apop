# CHANGELOG
## 2.2.1 (May 18, 2017)
* Actions
    * Add each action for parse fields of objects
    * Add dependency each action to other actions.
    
* Flow
    * Review parse algorithm. Parse from 0 level to deep.
    * More fast: object + 11%, array of object +33%
    
## 2.1.0 (May 12, 2017)

* Actions
    * Deprecate `pick` action
    ```js
      rmk.pick(config)(data)
      rmk.shortcuts.pick(config)(data)
    ```
    * Deprecate `recursive` action 
    ```js 
        rmk.action.recursive([
            rmk.(update|rename|toSnakeCase|toCamelCase|clear)(data),
            ...actions(data)
        ], deep = 8)(data)` 
    ```
    * Refactor and greatly increase perfomance ~ +10%

* Shortcuts
   * Deprecate use shortcuts actions as:
    ```js
      rmk.shortcuts.(update|rename|toSnakeCase|toCamelCase|clear)(data)
    ```
   * Add support use shortcuts as single action:
   ```js 
       rmk.(update|rename|toSnakeCase|toCamelCase|clear)(data)
   ```
   * Add support shortcut as recursive action:
    ```js 
        rmk.recursive.(update|rename|toSnakeCase|toCamelCase|clear)(data)
    ```
  
    
* Recursive flow
      
  * Add support recursive flow: 
  ```js
    rmk.recursive(
      rmk.(update|rename|toSnakeCase|toCamelCase|clear)(data),
      ...actions(data)
    )
  ```
  * Remove deep limit. Use a recursive flow with care.

* Single flow
    * Add support parse deep array [[[...]]]
 
* Docs
    * Update docs
    * Add config specific for all actions