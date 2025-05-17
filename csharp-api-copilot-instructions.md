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

# Copilot Instructions: .NET API Development
- If I tell you that you are wrong, think about whether or not you think that's true and respond with facts.
- Avoid apologizing or making conciliatory statements.
- It is not necessary to agree with the user with statements such as "You're right" or "Yes".
- Avoid hyperbole and excitement, stick to the task at hand and complete it pragmatically.

## I. C# Style

1.  **Variables:** `var` when type is clear.
2.  **Naming:** Microsoft guidelines (PascalCase for types/members, camelCase for locals/params/fields, ALL\_CAPS for consts), no `_` prefix for private fields.
3.  **Formatting:** Allman braces, 4 spaces indent.
4.  **Nulls:** `int?` for nullable value types, Microsoft standard operators (`?.`, `??`), explicit checks when needed.
5.  **Strings:** Interpolation (`$"..."`).
6.  **LINQ:** Fluent style, use extensively.
7.  **Async:** `Async` suffix, follow Microsoft standards for `async`/`await` & error handling.
8.  **Immutability:** Prefer immutable data structures where appropriate to enhance predictability and reduce side effects.

## II. Code Structure

1.  **Nesting:** Minimize via early returns & guard clauses (incl. inverted `if`).
2.  **Methods:** Short, focused (Clean Code/Pragmatic Programmer). Low complexity.
3.  **Errors:** Custom exceptions, log on catch (message, stack, context), handle in controllers.
4.  **Comments:** XML for public, "why" for internal (minimal).

## III. Solution/Project

1.  **Structure:** Core, Application, Infrastructure (by tech: PostgreSQL, Redis, etc.), Presentation (API), Tests (`[ProjectName].Tests.Unit`, `[ProjectName].Tests.Integration`).
2.  **Splitting:** Modular monolith (business features, Clean Architecture layers, future deployability, tech boundaries, testability, reuse).

## IV. Testing

1.  **Unit:** xUnit, Shouldly, Moq. Pragmatic TDD (value-driven, behavior focus). *(Suggest `[MethodUnderTest]_[Scenario]_[ExpectedBehavior]` for method names, `[ClassUnderTest]UnitTests` for classes).*
2.  **Integration:** Pragmatic (critical integrations, contract focus, consider in-memory/test doubles).

## V. Architecture

1.  **SOLID:** Pragmatic balance (context-dependent, avoid over-abstraction).
2.  **Patterns:** Apply known solutions (Repository, Service, DI common). Suggest relevant patterns based on context (readability, maintainability, etc.).

## VI. Configuration

* `appsettings.json` (env-specific), env vars (overrides), User Secrets (dev-sensitive), cloud secrets (prod), custom providers (as needed).

## VII. API & General

1.  **API:** RESTful.
2.  **Auth:** JWT.
3.  **DTOs/Mapping:** Use AutoMapper for convention-based object mapping.
4.  **Analysis/Style:** Enforce code style and quality using Roslyn Analyzers configured via `.editorconfig`.
5.  **Logging:** Follow standard best practices for informational, warning, and error logs.
6.  **Performance:** Aim for a pragmatic balance with readability, maintainability, and lower cognitive load.
