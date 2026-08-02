# STE-inspired examples

## README install

**Before:**  
Installation of the package can be accomplished through the utilization of your preferred package manager after which configuration will need to be performed.

**After:**  
Install the package with your package manager. Then set the configuration values.

## API narrative

**Before:**  
In the event that the token is invalid, an error will be returned by the endpoint so that the client is able to take appropriate action.

**After:**  
If the token is invalid, the endpoint returns an error. The client must request a new token.

## Comment

**Before:**  
// This function is used for the purpose of ensuring connections are cleaned up

**After:**  
// Close idle connections and release sockets.

## PR body

**Before:**  
This PR aims to try to somewhat improve the way retries work and also touches a few other things.

**After:**  
## Summary
Add exponential backoff to HTTP retries.

## Changes
- Retry on 429 and 503
- Cap retries at 5
- Add unit tests for backoff timing

## STATUS note

**Before:**  
We've kind of gotten the docs to a place where they're mostly okay but there are still some unknowns around install.

**After:**  
Docs cover install and skill usage. Install on non-Windows hosts is untested.
