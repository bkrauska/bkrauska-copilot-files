<rules>
    <notify>
    When you are done, use the #tool:show-notification tool to notify the user that you have completed the task.
    
    Set `sound` to `true`
    </notify>

    <edit_file>
    At the end of ANY conversation and changes to files are made turn with me where you create or edit a file for me:

    1. Stage all changes
    2. Commit the changes along with a short summary of the changes you made, and a bulleted list of the changes made by file.
    </edit_file>
</rules>

# Copilot Instructions: Angular 17 Web App Development

- If I tell you that you are wrong, think about whether or not you think that's true and respond with facts.
- Avoid apologizing or making conciliatory statements.
- It is not necessary to agree with the user with statements such as "You're right" or "Yes".
- Avoid hyperbole and excitement, stick to the task at hand and complete it pragmatically.

## I. TypeScript Style (Adapted from C# Preferences)

1.  **Variables:** `const` by default, `let` if reassignment is needed. Type inference encouraged, but explicit types for clarity in complex scenarios or public APIs.
2.  **Naming:** Follow Angular Style Guide (camelCase for most identifiers, PascalCase for classes/interfaces/enums/components/directives/pipes).
3.  **Formatting:** Follow Prettier conventions (integrate with your editor).
4.  **Nulls/Undefined:** Use strict null checking. Leverage optional chaining (`?.`) and nullish coalescing (`??`).
5.  **Strings:** Template literals (` `` `) for embedding expressions.
6.  **RxJS:** Use extensively for asynchronous operations and state management.
7.  **Async/Await:** Use for cleaner asynchronous code, especially for Promises.

## II. Angular Code Structure

1.  **Component Files:** Separate `.html` (template). Avoid `.css`, `.scss`, etc., (use Tailwind CSS).
2.  **Component Architecture:** Smart (Container) / Dumb (Presenter) pattern. Favor specific, reusable components (e.g., `phone-input`) over generic ones.
3.  **Services:** Use for business logic, data fetching, and state management (with RxJS).
4.  **Modules:** Organize application features into logical Angular modules.
5.  **Error Handling:** Handle errors in the calling component (services reject Promises on API errors).

## III. State Management (RxJS in Services)

1.  Use private `Subject`, `BehaviorSubject`, or `ReplaySubject` to hold state within services.
2.  Expose state as public, read-only `Observable` properties using `.asObservable()`.
3.  Components subscribe to these Observables to observe state changes.

## IV. Data Fetching (Custom HttpClient Wrapper & Promises)

1.  Use a custom service wrapper around Angular's `HttpClient`.
2.  Perform API calls using Promises (via `toPromise()`).
3.  Services reject the Promise on API errors, allowing components to handle them.
4.  Minimal client-side data transformation; work with API data directly.

## V. Testing (Pragmatic TDD with TestBed)

1.  Apply a pragmatic TDD approach, focusing on component behavior and service logic.
2.  Use Angular's `TestBed` for setting up testing environments.
3.  Mock dependencies to isolate units under test (using `jasmine.createSpyObj()` or a mocking library if adopted).
4.  Prioritize testing critical user flows and complex logic.

## VI. Security

1.  **XSS Prevention:** Use Angular's security context and `DomSanitizer`.
2.  **CSRF Handling:** Implement handling of CSRF tokens if the backend uses them.
3.  **Input Validation:** Implement robust client-side validation using Angular Forms.
4.  Keep Angular and dependencies updated.

## VII. Build and Deployment (Best Practices)

1.  Use production builds (`--prod`) with AOT compilation and tree-shaking.
2.  Implement lazy loading for modules.
3.  Manage environment-specific configurations using `environment.ts` files.

## VIII. Styling

1.  Primary styling using Tailwind CSS (avoid component-specific style files).
