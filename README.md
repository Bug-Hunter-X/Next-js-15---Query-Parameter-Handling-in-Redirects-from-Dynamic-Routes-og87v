# Next.js 15 Query Parameter Bug

This repository demonstrates a bug encountered in Next.js 15 related to query parameter handling during redirects. Specifically, when redirecting from a dynamic route to a page route, the query parameters might not be properly transferred.

## Bug Description

The issue occurs when using `router.push` to redirect from a dynamic route (e.g., `/about`) to a page route (e.g., `/`) with query parameters. The intended behavior is that the query parameters should be appended to the URL upon redirection. However, in some cases, these parameters are lost or not correctly handled.

## Reproduction Steps

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm run dev` to start the Next.js development server.
4. Navigate to the `/about` page.
5. Click the button to redirect to the home page with a query parameter.
6. Observe that the query parameter is either missing or not correctly handled on the home page.

## Expected Behavior

The home page should receive the query parameter (`name=John Doe`) after the redirect.

## Actual Behavior

The query parameter is either missing or not correctly appended to the URL.

## Workaround

This bug is likely due to how Next.js handles query parameters during redirects from dynamic routes. A potential workaround is to explicitly handle the query parameters in the home page component, reading them from `router.query`.