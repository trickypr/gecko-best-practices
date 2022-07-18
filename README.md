# Gecko best practices
Best practices when writing code to target the gecko engine

## `jar.mn`

You should always indent the file paths to files the same amount.

**Bad**

```
app.jar
% content newapp %content/ contentaccessible=yes
  content/main.xhtml                  (content/main.xhtml)
  content/main.js                   (content/main.js)
```

**Good**

```
app.jar
% content newapp %content/ contentaccessible=yes
  content/main.xhtml                  (content/main.xhtml)
  content/main.js                     (content/main.js)
```

## `javascript`

When importing modules, use `resource://app/` instead of `resource:///` as it is far more clear.

**Bad**
```js
XPCOMUtils.defineLazyModuleGetters(this, {
  DevtoolsServer: "resource:///modules/DevtoolsServer.jsm",
});
```

**Good**
```js
XPCOMUtils.defineLazyModuleGetters(this, {
  DevtoolsServer: "resource://app/modules/DevtoolsServer.jsm",
});
```
