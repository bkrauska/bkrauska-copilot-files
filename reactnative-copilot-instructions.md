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

# Copilot Instructions: React Native App Development (Concise)
- If I tell you that you are wrong, think about whether or not you think that's true and respond with facts.
- Avoid apologizing or making conciliatory statements.
- It is not necessary to agree with the user with statements such as "You're right" or "Yes".
- Avoid hyperbole and excitement, stick to the task at hand and complete it pragmatically.

## I. JavaScript/TypeScript Style (Adapted Preferences)

1.  **Variables:** `const` by default, `let` if reassignment is needed. Encourage TypeScript for type safety.
2.  **Naming:** Follow standard JavaScript/TypeScript and React Native conventions (camelCase for variables/functions, PascalCase for components).
3.  **Formatting:** Follow Prettier conventions (integrate with your editor).
4.  **Nulls/Undefined:** Use strict null checks if using TypeScript. Leverage optional chaining (`?.`) and nullish coalescing (`??`).
5.  **Asynchronous Operations:** Use `async/await` with Promises for cleaner asynchronous code.
6.  **State Management:** Favor functional components with React Hooks (`useState`, `useEffect`, `useContext`, `useReducer`). For more complex state, consider libraries like Zustand or Redux Toolkit following pragmatic principles.
7.  **Immutability:** Prefer immutable data structures and patterns for predictable state updates.

## II. React Native Code Structure

1.  **Component Organization:** Small, reusable functional components where possible. Separate UI logic from business logic using custom Hooks or utility functions.
2.  **Styling:** Primarily use StyleSheet API for performance and maintainability. Consider Tailwind CSS Native or similar utility-first approaches if preferred for rapid styling.
3.  **Error Handling:** Implement `try/catch` blocks for asynchronous operations and provide user-friendly error messages. Consider global error handling mechanisms.
4.  **Comments:** Use clear, concise comments explaining non-obvious logic or platform-specific behavior.

## III. State Management (React Hooks & Potential Libraries)

1.  **Local State:** Use `useState` for simple component-level state.
2.  **Context API:** Use `useContext` for sharing state that is global to a smaller part of the component tree.
3.  **Complex State (if needed):** Consider Zustand (simpler) or Redux Toolkit (more structured) with a pragmatic approach, focusing on value and maintainability. Follow recommended patterns for actions, reducers/slices, and selectors.

## IV. Data Fetching (Promises with Async/Await)

1.  Use `fetch` API or a library like Axios for making API calls.
2.  Employ `async/await` for cleaner asynchronous code.
3.  Implement error handling within the data fetching logic (e.g., `try/catch`).
4.  Consider creating custom hooks or utility functions to encapsulate data fetching logic.

## V. Testing (Pragmatic Approach with Jest & React Native Testing Library)

1.  Apply a pragmatic testing approach, focusing on component behavior and business logic.
2.  Use Jest as the primary testing framework.
3.  Utilize React Native Testing Library for testing component interactions from a user's perspective.
4.  Mock dependencies (API calls, services) using `jest.fn()` or mocking libraries.
5.  Prioritize testing key user flows and critical functionality.

## VI. Security (Web Security Principles Apply)

1.  **XSS Prevention:** Be mindful of rendering external content and sanitize where necessary (though less of a direct issue than in web).
2.  **Input Validation:** Implement thorough input validation on the client side.
3.  **Secure Storage:** Use secure storage options for sensitive data (e.g., `react-native-keychain`).
4.  Keep dependencies updated.

## VII. Build and Deployment (Platform Specific)

1.  Follow standard React Native build processes for iOS (Xcode) and Android (Gradle).
2.  Utilize environment variables (e.g., using `react-native-config`) for different build environments.
3.  Optimize assets (images, fonts) for production builds.

## VIII. Styling

1.  Primarily use React Native's StyleSheet API.
2.  Consider Tailwind CSS Native or similar for utility-first styling if it aligns with project needs.
