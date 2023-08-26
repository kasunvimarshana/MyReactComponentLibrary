# npm init
# npm install --save-dev @types/node @types/react @types/react-dom react react-dom typescript
# add peer dependencies
"peerDependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
}
# add [main, module, files] section
"main": "dist/cjs/index.js",
"module": "dist/esm/index.js",
"files": [
    "dist"
],
# add [scripts] section
"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "build": "rm -rf dist/ && prettier --write src/ && npm run build:esm && npm run build:cjs",
    "build:esm": "tsc",
    "build:cjs": "tsc --module CommonJS --outDir dist/cjs"
},