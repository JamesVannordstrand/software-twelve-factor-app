# Twelve-Factor App
The Twelve-Factor App is a methodology for building software-as-a-service applications with a focus on portability across execution environments and a clear contract with the underlying operating system. The methodology was created by Adam Wiggins, a co-founder of Heroku, and it outlines best practices for building modern, scalable, maintainable software applications. Below is an overview of the twelve factors:

## Codebase
- One codebase, tracked in revision control, for each app.
- Multiple deploys can come from the same codebase.

## Dependencies
- Explicitly declare and isolate dependencies.
- Do not rely on implicit existence of system-wide packages.

## Config
- Store configuration in the environment.
- Keep config separate from code.

## Backing Services
- Treat backing services (like databases, messaging systems, etc.) as attached resources.
- Interact with them through a URL or other locator stored in the configuration.

## Build, Release, Run
- Separate build and run stages.
- Each release should have a unique ID and contain a compiled build and the environment config.

## Processes
- Run the app as one or more stateless processes.
- Any data that must persist should be stored in a stateful backing service, like a database.

## Port Binding
- Expose services via port binding.
- Do not rely on runtime injection of a webserver into the execution environment to create a web-facing service.

## Concurrency
- Scale out via the process model.
- Run multiple processes of your app to handle load.

## Disposability
- Maximize robustness with fast startup and graceful shutdown.
- Processes should be disposable, facilitating fast elastic scaling, rapid deployment, and robustness in the face of failure.

## Dev/Prod Parity
- Keep development, staging, and production as similar as possible.
- All environments should be as close as possible to avoid "works on my machine" type issues.

## Logs
- Treat logs as event streams.
- Don't manage log files in the app, but instead write logs to stdout so they can be handled by the execution environment.

## Admin Processes
- Run admin/management tasks as one-off processes.
- Use the same code and environment as the regular long-running processes of the app, but run them as one-off processes like database migrations, console sessions, etc.