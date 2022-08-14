Challenge: https://github.com/tj-oconnor/cyber-open-2022/tree/main/web/black-friday

Write-up: https://ctftime.org/task/22986


# Script Outline
## Initial Investigation
1) Looking at the website
  - highlight the ability to change stores

2) Note that a cookie changes the store
  - Can see the function in the source code
  - Can see the cookie in dev tools
  - Can see + edit the cookie by intercepting GET request in Burp

## Discovering Potential Exploits
3) Can mess with cookie value in Burp to get different results
  - Discovering SQL vulnerability
    - Insert "'" to get an error
    - Insert "AND 1=2" to get Store Not Found
    - Insert "AND 1=1 to get nothing
  - This means that Blind SQL injection is possible
4) FIngerprinting the DBMS
  - Identified SQLlite by running a type specific command

## Solving
5) Scripting blind SQL injection
  - Explain the process to solve it instead of specifically analyzing the script (maybe highlight the parts of the script that addresses each problem?)
6) Show script running and the solve:)
  
