# Reflection

**Ensuring functionality and security.**  
I start from explicit requirements and encode them as unit tests (red-green-refactor). For the contact service, this meant tests for invariant rules (e.g., non-null fields, length bounds, immutable/unique IDs, and a 10-digit phone format), plus negative tests that assert the correct exceptions. I complement this with boundary tests, code reviews, and static analysis where available. Security-wise, I validate and sanitize inputs, avoid logging PII, use clear exception messages without leaking data, and keep data encapsulated to minimize unintended mutation.

**Interpreting user needs and incorporating them.**  
I translate stakeholder needs into user stories with acceptance criteria, then create tests that mirror those criteria (test names reflect the requirement for traceability). When behavior is ambiguous, I prototype quickly and iterate based on feedback. In the contact service, user needs boiled down to simple, reliable CRUD with strict validation; this guided method design, error handling, and the structure of the test cases.

**Approach to software design.**  
I aim for small, composable units with clear responsibilities (SOLID). I design the domain model first (`Contact`) and then the orchestration layer (`ContactService`) that enforces business rules. I prefer interface-driven development, meaningful names, and defensive programming (e.g., validating before state changes). Tests drive the API shape and keep refactors safe. The result is code that’s readable, testable, and easy to extend—for example, swapping an in-memory store for a persistent repository without changing tests or callers.
