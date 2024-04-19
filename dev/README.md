# K19B Dev Docs
To ensure that Kalium.Core and plugins can be build/run on most modern PCs, source code can be easily read by most developers, please read this docs before contributing.  

## Typescript
Kalium.Core is a Node.JS + Typescript project, ensure (1) your code can be build/run on following Node.JS versions:  
- Node.JS 16 LTS
- Node.JS 18 LTS
- Node.JS 20
- Node.JS latest

(2) Kalium.Core code does not exceed JS version ``es2020``  
```json
{
  "compilerOptions": {
    "target": "es2020"
  }
}
```

(3) plugin code does not exceed JS version ``es2016``, and generate code for ``node16``  
```json
{
  "compilerOptions": {
    "target": "es2016",
    "module": "node16",
    "moduleResolution": "node16"
  }
}
```

(4) when compiling TS code to JS, set JS/mjs/map/dts dir to ``./dist``  
```json
{
  "compilerOptions": {
    "outDir": "./dist"
  }
}
```

## Styles
(1) if-else example
```typescript
if (a == 1) {
    todo(something);
} else {
    elsedo(something);
}
```
Place the first ``{`` and ``(condition)`` in the same line, ``} else {`` in same line.  

```typescript
if (a == 1) todo something; // DONT do this
```
Do not omit ``{`` ``}``  

(2) consts & vars naming
- Global consts: ``NAMINGJUSTLIKETHIS``
- other consts, vars, function names... : ``namingJustLikeThis``

(3) uglify
Allow the use of these abbreviations in all code:  
```typescript
if (numberA != numberB) {
    return !0; // (a) !0 is true
} else {
    return !1; // (b) !1 is false
}
let someVar: string | undefined = void(0); // (c) void(0) is undefined
```

## Commit Message
- refactor: no fix or feat, just code rewrite
- fix: fix bugs
- feat: new feature
- style: style fix
- perf: performance optimization
- chore: deps or submodules change
- misc: other like code cleanup

If you really can't think of anything commit message, use ``--allow-empty-message`` to commit.(dont do this in dev/main branch or PRs)

## Language
- Use English in code comments, issues/PRs title, commit message.
  But if it is a proper noun and doesn't have a good translate in English, you can use any language.
- If you want write issue/PR in your language(not English), please attach a translation from translate.google.com.
