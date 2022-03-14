# Twin Output Tester

This repo is a sandbox to see the babel output from twin.macro.

It’s useful for testing new features or to see what output gets created by twin.

## Usage

1. Pull down both this repo and the `twin.macro` repo into a common projects folder.
2. Cd into the repo `twin-output-tester`
3. In `package.json`, update the location of the twin.macro repo in the `dev` script:
   ```json
   {
     "scripts": {
       "dev": "nodemon --watch ~/[YOUR_PROJECT_FOLDER]/twin.macro/macro.js --watch index.tsx --watch tailwind.config.js --watch babel.config.js --watch package.json -x \"npm run build:dev\" --delay .01"
     }
   }
   ```
4. Link the `twin.macro` repository within node_modules, eg: `npm link ./../twin.macro`
5. Run `npm run dev` to start the dev server.
6. In a separate code editor window, make any changes to `twin.macro`, while running it’s dev server `npm run dev`.

This repo will automatically rebuild once the twin.macro repo has built it’s `macro.js` file.
