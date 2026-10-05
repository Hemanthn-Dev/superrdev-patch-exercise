# Patch Notes

## What I fixed

1. Fixed SQL operator precedence in `TaskRepository` so archived tasks are excluded and the status filter applies correctly to title/description matches.

2. Removed the artificial `Thread.sleep()` from `TaskController` to avoid unnecessary blocking and request latency.

3. Added validation for `page` and `pageSize`. Invalid pagination now returns HTTP 400, with `pageSize` limited to 100.

4. Improved frontend request handling in `useTasks.js` by clearing previous errors, clearing stale data on failure, and always resetting loading state with `finally()`.

5. Updated `App.jsx` so changing search or status resets pagination to page 1.

## What I did not change

I kept the patch focused and did not rewrite unrelated parts of the application. Invalid status values and other lower-priority issues were left unchanged.

## Testing

I manually tested search/status filtering, pagination validation, filter pagination reset, normal task loading, and frontend error handling.

## AI assistance

I used AI assistance to identify potential bugs, understand their impact, and review fixes. I inspected and tested the changes myself before keeping them.