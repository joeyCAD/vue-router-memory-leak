# vue-router memory leak report

## How to repetition

```shell
npm i

npm run build

npm run preview
```

(Assumes you're using a chome like browser)

- Open up devtools command runner (`ctrl+shift+p`), search/select 'show performance monitor' to see live dom nodes easier while testing
- Switch between the Empty page and other pages with lots of nodes and end up on the Empty page, manually GC (command runner `ctrl+shift+p` 'collect garbage') and observe the dom nodes go down to the expected Empty page amount in the 'performance monitor' tab
- This time switch from one page with alot of nodes to another and manually GC, observe that the dom nodes go down as expected to the current pages expected amount. Now switch back to the Empty page and observe that the dom nodes still remain at the same amount as the page that was GC'd on
- The only way ive found to 'free' those nodes is to go back to BEFORE the page that was GC'd on, then go to the Empty page again and manually GC
