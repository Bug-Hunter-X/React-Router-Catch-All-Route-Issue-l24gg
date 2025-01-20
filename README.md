# React Router Catch-All Route Bug
This repository demonstrates a common issue in React Router v6 where a catch-all route (`*`) can unintentionally override other routes if not placed carefully within the route hierarchy. The improper placement can lead to other routes never being matched.

## Bug Description
The bug lies in the order and placement of routes.  The catch-all route `path="*"` is too broadly defined, matching all paths before other specific routes have a chance to match. This prevents the `/` and `/about` routes from ever being accessed.

## Solution
The solution involves proper route ordering. The catch-all route should always be placed last in the routes array.  Only when all other routes have been checked should this catch-all route be triggered.