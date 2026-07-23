1. angular.json
This file contains the Angular workspace configuration, including project build, serve, test, assets, styles, scripts, and production build settings.

2. tsconfig.json
This file contains the base TypeScript compiler configuration used by the Angular project.

3. tsconfig.app.json
This file contains TypeScript compiler settings specific to the Angular application source code.

4. package.json
This file contains the project metadata, npm scripts, dependencies, and development dependencies required by the Angular application.

5. src/main.ts
This is the main entry point of the Angular application that bootstraps the root application and starts the Angular application.

6. src/app/app.config.ts
This file contains the application-level configuration and providers used by the standalone Angular application.

7. src/app/app.ts
This file defines the root Angular component, including its component metadata, template, styles, and application logic.

8. src/index.html
This is the main HTML file loaded by the browser and contains the root HTML element where the Angular application is rendered.


Compiled Application Code:
The compiled Angular application code is generated in the main.js file inside the dist/student-course-portal/browser folder.




Build Budgets:
The initial bundle has a maximumWarning threshold of 4kB and a maximumError threshold of 8MB. maximumWarning specifies when Angular displays a warning about the bundle size, while maximumError specifies the size limit at which Angular reports a build error.


architect
    ↓
build
    ↓
configurations
    ↓
production
    ↓
budgets
    ↓
maximumWarning
maximumError
