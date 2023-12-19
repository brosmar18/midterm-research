# (folderName) in Next.js

## Overview
In Next.js, `(folderName)` is a convention used to denote a Route Group within the `app` directory. This helps organizing project files and route segments logically. 

## In Simple Terms: 
Using `(folderName)` lets you group related files or routes together in Next.js without changing the URL structure of your app. 

## Key Terms: 
- **Route Group**: A way to group routes or files in Next.js
- **URL Path**: The path of the URL that represents a specific webpage. 

## Syntax
```js
 // Structure within the `app` directory
 app/
   (folderName)/
     page.js
```

## Example
```js
 // Example of a route group
 app/
   (marketing)/
     about/
       page.js  // URL path: /about
 
```

### Breakdown 
- **Wrapping with Parentheses**: The folder name is wrapped in parentheses. 
- **No URL Path Change**: The name of the route group doesn't appear in the URL path
    - The folder designed as a Route Group, denoted by enclosing the folder name in parentheses like `(folderName)`, does not contribute to the URL path of the pages within the group. 
    - For example: 
        - If you have a file at `app/(marketing)/about/page.js`, the URL path to access this page would be `/about`, not `/marketing/about`. The `(marketing)` part, despite being a folder name, is omitted from the URL, serving soley for organizational purposes within the project structure. 

## Summary 

In Next.js `(folderName)` is used to create a Route Group that organizes files and routes without affecting the URL path. This approach enhances project structure management without influencing the app's routing behavior. 

## Citations

- Next.js Documentation. (n.d.). Route Groups. Retrieved from [Next.js Docs](https://nextjs.org/docs/app/building-your-application/routing/route-groups#convention)
