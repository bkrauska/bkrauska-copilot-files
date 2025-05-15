# Copilot Instructions: Swift macOS App Development (Concise)

## I. Swift Style (Adapted Preferences)

1.  **Variables:** Use `let` for constants and `var` for variables. Emphasize strong typing.
2.  **Naming:** Follow Swift API Design Guidelines (camelCase for variables/functions/methods, PascalCase for types/protocols/enums/structs).
3.  **Formatting:** Follow SwiftFormat conventions (integrate with Xcode).
4.  **Optionals:** Use optionals (`?`) to handle the absence of a value. Leverage optional binding (`if let`, `guard let`) and optional chaining (`?.`).
5.  **Asynchronous Operations:** Use `async/await` for concurrent code. Consider `Combine` framework for reactive programming if the project adopts it.
6.  **State Management:** Favor value types (structs, enums) for state. For complex state, consider MVVM with Combine or RxSwift, or the Redux-like architecture with libraries like ReSwift, following pragmatic principles.
7.  **Immutability:** Prefer immutable data structures (`let`) where appropriate for predictable state and reduced side effects.

## II. macOS Code Structure

1.  **Component Organization (Views/View Controllers):** Small, focused views (`NSView`) and view controllers (`NSViewController`). Separate UI logic from business logic using view models or presenters. Use Storyboards/XIBs or programmatic UI.
2.  **Styling:** Primarily use programmatic UI or Storyboards/XIBs with `IBOutlet` and `IBAction` connections. Leverage Auto Layout constraints for flexible UI. Consider using a styling framework if preferred for consistency.
3.  **Error Handling:** Use Swift's `Error` protocol and `Result` type for robust error handling. Provide user-friendly error alerts or notifications.
4.  **Comments:** Use `///` for documentation comments and clear, concise comments for non-obvious logic or macOS-specific behavior.

## III. State Management (MVVM or Similar)

1.  **Model-View-ViewModel (MVVM):** A preferred architectural pattern. Models encapsulate data, ViewModels prepare data for display and handle user input, and Views (NSViews, NSViewControllers) display the data and forward user actions.
2.  **Bindings:** Use property observers (`didSet`), delegation, closures, Key-Value Observing (KVO), or reactive programming frameworks (Combine, RxSwift) to bind ViewModels to Views.
3.  **State Containers (if needed):** For more complex state, consider a Redux-like architecture with a single source of truth.

## IV. Data Fetching (Promises/Async-Await or Combine)

1.  Use `URLSession` for making network requests.
2.  Employ `async/await` for handling asynchronous responses. Consider using Combine's `Publisher` for a more reactive approach.
3.  Implement robust error handling for network requests.
4.  Create dedicated services or managers to encapsulate data fetching logic.

## V. Testing (Pragmatic Approach with XCTest)

1.  Apply a pragmatic testing approach, focusing on unit testing business logic (ViewModels, services) and UI testing key user interactions.
2.  Use XCTest as the primary testing framework.
3.  Mock dependencies (network requests, data stores, system services) using protocol-based mocking or libraries.
4.  Prioritize testing critical functionality and areas prone to change.

## VI. Security (Platform and Web Principles)

1.  **Secure Data Storage:** Use Keychain Services for storing sensitive information.
2.  **Input Validation:** Implement thorough input validation.
3.  **Secure Communication (HTTPS):** Ensure communication with backends is over HTTPS.
4.  Be mindful of handling sensitive data in memory.
5.  Follow macOS-specific security guidelines (e.g., sandboxing).
6.  Keep dependencies updated.

## VII. Build and Deployment (Xcode)

1.  Follow standard macOS build and deployment processes using Xcode.
2.  Utilize build configurations and environment variables for different environments.
3.  Code signing and notarization for distribution.
4.  Optimize assets and build settings for production.

## VIII. Styling

1.  Primarily use programmatic UI or Storyboards/XIBs with Auto Layout.
2.  Consider using styling frameworks or utility libraries if preferred for consistency.
