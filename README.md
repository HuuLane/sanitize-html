origin repo: https://github.com/apostrophecms/sanitize-html

I have hacked it to add `disallowedStyles` for special purpose.

```js
const r = sanitizeHtml(
  "<span style='color: blue; text-align: justify; font-family: helvetica'></span>",
  {
    allowedTags: false,
    allowedAttributes: {
      span: ["style"],
    },
    disallowedStyles: ["text-align", "font-family"],
  }
);

r === '<span style="color:blue"></span>';
```
