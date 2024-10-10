# Local Instance Instructions

System Requirements:

- Visual Studio Code: https://code.visualstudio.com/
- Git: https://git-scm.com/downloads
- Node 18.17 or later: https://nodejs.org/en
- Python 3.12: https://www.python.org/downloads/

1. Ensure that you have all of the system requirements installed
2. Open Visual Studio Code
3. Open a new terminal using the following command:

````
Windows:    CTRL + SHIFT + ~
MacOS:      CMD + SHIFT + ~  ```
````

4. Install dependencies for the backend application using the following commands in your terminal:

```bash
cd apps/backend     # change directory to apps/backend
npm i               # install dependencies defined in package.json
```

5. After installing backend dependencies, install dependencies for the backend application in your termainal:

```bash
cd ..               # move out of frontend directory
cd frontend         # change directory to frontend, from apps folder
npm i               # install dependencies defined in package.json
```

6. Boot up the developement server:

```bash
npm run dev
```

Or to kill the development server...

```
Windows:    CTRL + C
MacOS:      CMD + C
```

## Firebase Functions

Note: This is under the assumption that you have everything set up for the backend.

- The TypeScript portion of the backend is developed for the purpose of deploying APIs.
- The Python portion of the backend (not yet implemented) is for backing up, and managing already existing data.
- Ensure that you have Firebase CLI installed using the following command:

```bash
npm i -g firebase-tools
```

1. To develop a Firebase Function, you create a '.ts' file within the functions folder. I recommend that we keep this organized, but not to an over-engineered extent. For example, we can have a folder dedicated to all functions related to a specific collection. We decide this a group and it wil be documented.
2. You will then need to export this within the barrel file (index.ts inside of the functions folder) so that the Firebase CLI can resolve back to the rest of your functions within the main entry point (index.ts inside of the src folder).
3. After that is all done, you can deploy that function to Firebase using the command applicable to your use case:

````bash
firebase deploy --only functions                        # this will deploy all functions exported
firebase deploy --only functions:[nameOfFunction]       # this will deploy the specified function, which saves time```
````
