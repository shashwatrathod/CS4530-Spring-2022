# Covey.Town

Covey.Town provides a virtual meeting space where different groups of people can have simultaneous video calls, allowing participants to drift between different conversations, just like in real life.
Covey.Town was built for Northeastern's [Spring 2021 software engineering course](https://neu-se.github.io/CS4530-CS5500-Spring-2021/), and is designed to be reused across semesters.
You can view our reference deployment of the app at [app.covey.town](https://app.covey.town/) - this is the version that students built on, and our [project showcase](https://neu-se.github.io/CS4530-CS5500-Spring-2021/project-showcase) highlights select projects from Spring 2021.

<!-- TODO: Introduction to this tutorial -->
<!-- TODO: Table of contents -->

## Environment Variables

### Introduction to Environment Variables

Environment variables are variables that are set outside of a program, generally through a cloud provider or operating system. The primary use for these variables is to limit the need to modify an application due to changes in configuration data. For example, when `SOME_API_I_USED_IN_MY_APP`'s URL changes there’s no need for source code alterations, testing, and deployment of the modified application. Modifying and releasing application code is relatively complicated and increases the risk of introducing undesirable side effects into production.
Use cases for environment variables include but are not limited to data such as:

- Execution mode (e.g., production, development, staging, etc.)
- Domain names
- API URL/URI’s
- Public and private authentication keys (only secure in server applications)
- Service account names

In Node, during application initialization, these environment variables are loaded into `process.env`. They can be accessed by suffixing the name of the environment variable as shown below:

```typescript
let apiUrl: string | undefined = [process.env.SOME_API_I_USED_IN_MY_APP];
```

Environment variables can be stored in a `.env` file at the root level in the project directory.

```
SOME_API_I_USED_IN_MY_APP="https://random-data-api.com/api/"
SUPER_SECRET_API_KEY="CS4530SP22"
```

NOTE: Sometimes, these `.env` files can contain critical data like private keys, tokens, internal API endpoints, etc. It is therefore advised to never expose this file to public.

You can read more about environment variables in Node [here](https://medium.com/chingu/an-introduction-to-environment-variables-and-how-to-use-them-f602f66d15fa).
