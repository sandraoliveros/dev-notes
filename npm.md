
# NPM 📦


## Quick init
This starts a `package.json` without having to ask the questions:
```
npm init -y
```

## Symbols next to version number
- `^` 👈 This symbol means that the **major** version will be **unchanged**.
- `~` 👈 This symbol will keep **major** and **minor** versions **unchanged**. Only patch versions will be updated.

## Update package version

To understand this let's do it by example. We're going to start by installing `jquery`:
```
npm i jquery@2.1.0
```
In the `package.json` appears the following:
```
"jquery": "^2.1.0"
```
Note the caret. Now, if we do
```
npm update jquery
```
the minor and patch versions are changed **but the major version is kept**.
```
"jquery": "^2.2.4"
```
Let's back to the initial version and remove the caret. What happen now when we run `npm update jquery`?
```
"jquery": "2.1.0"
```
The version is not updated!! In this case, if we want to change the version we can install it manually or we can run
```
npm i jquery@latest
```
👆 It is the only way to change the major version without knowing the number of the version. It install the last published major version.

## npx

`npx` is a relatively new feature in `npm`. It can be used to run binary files that are stored in the `node_modules/.bin` directory. Let's say that you want to run `babel` from the command line. Usually you'd run `./node_modules/babel`. With `npx` you don't need to do this anymore: you can do `npx babel` and it would be the same since the binary for `babel` will be added to the `node_modules/.bin` directory when you install `babel`.
