# Unhandled Promise Rejection in NextAuth Session

This repository demonstrates a common issue encountered when using NextAuth.js within Next.js API routes.  The problem arises from improper handling of asynchronous operations, specifically when attempting to access the session within an API route before the `unstable_getServerSession` promise resolves.  This can lead to unhandled promise rejections and unexpected behavior.

## The Problem

The provided `bug.js` demonstrates the issue:  The API route attempts to access `session` before the `unstable_getServerSession` call has fully completed.  This causes a race condition, resulting in an unhandled rejection if the session is not immediately available.

## The Solution

The `bugSolution.js` provides a fix by using an `async` function and `await` to ensure the `unstable_getServerSession` promise resolves before proceeding.

## Setup

1. Clone the repo
2. Install dependencies: `npm install`
3. Run the development server: `npm run dev`

## Note

Remember to replace placeholder values for `authOptions` with your actual configuration.