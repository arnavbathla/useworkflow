# Vercel Workflow Directive Demo for AI Agents

This project is a [Next.js](https://nextjs.org) application, bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app), specifically designed to demonstrate and test Vercel's `useworkflow` directive. Its primary purpose is to showcase how this powerful directive can be leveraged to build and ship robust, long-running, and fault-tolerant background AI Agents, which is particularly relevant for orchestrating complex processes like those involved in shipping AI Agents.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

*   **Vercel `useworkflow` Directive:** Core demonstration of its capabilities for orchestrating background tasks and long-running operations.
*   **AI Agent Orchestration:** Highlights how `useworkflow` can be used as a foundation for building and managing complex AI agent workflows.
*   **Fault-Tolerant Steps:** Individual workflow steps are designed to be retried automatically on unhandled errors, ensuring robustness.
*   **Explicit Error Handling:** Demonstrates the use of `FatalError` to prevent retries for unrecoverable issues (e.g., an invalid email format).
*   **Next.js Integration:** Seamlessly integrates with Next.js API routes and the App Router for triggering workflows from the frontend.
*   **Asynchronous Execution:** Workflows execute asynchronously, ensuring the main application thread remains responsive and non-blocking.

## Project Structure

*   `app/page.tsx`: The main frontend page containing a simple email signup form.
*   `app/api/signup/route.ts`: The Next.js API route responsible for receiving signup requests and initiating the `handleUserSignup` workflow.
*   `workflows/user-signup.ts`: Defines the `handleUserSignup` workflow, which is composed of several `use step` functions (`createUser`, `sendWelcomeEmail`, `sendOnboardingEmail`). This file contains the core business logic and workflow orchestration.
*   `next.config.ts`: Configures Next.js to enable the `workflow` integration using `withWorkflow`.
