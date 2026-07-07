---
icon: lucide/list-checks
---

# Instructions for documenting projects

Use this page as a guideline to creating a new project entry under `docs/Projects/`. Whether the project is a research activity, thesis/student project or just a test/demo, please follow a methodical system for documenting your project. You can use the provided [template](2026-Example-Project/index.md) as a foundation for your projects documentation. 

Projects should be added into their own **named** folders in the *Projects/* folder, for example *Projects/2026-VDA5050-Crane/* 

If the project contains multiple markdown files, they can be easily re-ordered by adding a number in front of the name, for example *1-instructions.md* and *2-setup.md*. This way they appear in the wanted order in the documentation tree. 

!!! success "Main rule"

    Document the project so that a new person can understand the goal, rebuild the setup, run the main workflow, find the outputs, and know what is safe or unsafe without asking the original maintainer.

## When to create a new project folder

Create a new folder when the work has any of the following:

| Case | Create project folder? | Example |
|---|---:|---|
| Research experiment | Yes | Navigation benchmark, fleet coordination, digital twin integration |
| Student project | Yes | Master's thesis experiment, course project, summer assistant work |
| Temporary test | Yes, if it changes setup or creates reusable results | Testing a new sensor driver or ROS 2 package |
| One-off note | Usually no | Meeting note with no technical output |
| Platform-wide procedure | No, put it in main docs | General robot startup, charging, safety procedure |

## Naming convention

Use a lowercase slug:

``` text
YYYY-short-topic-name
```

Good examples:

``` text
2026-navigation-benchmark
2026-fleet-digital-twin-demo
2026-lidar-mount-test
2026-student-thesis-person-following
```

Avoid names such as:

``` text
new-test
cool-project
final-version
robot-stuff
```

!!! warning "Avoid personal-only names"

    Names should reflect the project's purpose, not its author. People leave; the project lives on.

## Example project folder layout

=== "Small project"

    Use this for short tests or early prototypes.

    ``` text
    docs/Projects/2026-example-test/
    ├── index.md
    └── assets/
    ```

=== "Normal project"

    As the small project grows, try to divide different sections into their own files/pages. Example for research, student, and integration projects.

    ``` text
    docs/Projects/2026-example-project/
    ├── index.md
    ├── setup.md
    ├── operation.md
    ├── experiments.md
    ├── troubleshooting.md
    └── assets/
        ├── diagrams/
        ├── photos/
        └── configuration-snapshots/
    ```

=== "Large project"

    If the project becomes very large, it's a good idea to include a page describing the architecture and structure of the whole project. Use this when the project has several work packages or multiple maintainers.

    ``` text
    docs/Projects/2026-example-large-project/
    ├── index.md
    ├── architecture.md
    ├── setup.md
    ├── operation.md
    ├── experiments/
    │   ├── index.md
    │   ├── experiment-001.md
    │   └── experiment-002.md
    ├── troubleshooting.md
    └── assets/
        ├── diagrams/
        ├── photos/
        └── configuration-snapshots/
    ```

## How to create a new project page

1. Duplicate the [template folder](2026-Example-Project/index.md) into `docs/Projects/` and name it [appropriately](#naming-convention).
2. Replace every `TODO` placeholder.
3. Add setup commands that have been tested from a clean workstation.
4. Add links to repositories, data folders, configuration files, and maps.
5. Add screenshots, diagrams, or photos under the project `assets/` folder.
6. Run a local documentation preview and check that links work.

``` bash title="Preview documentation"
zensical serve
```

## What good documentation should answer

A future maintainer should be able to answer these questions from the project page:

- What was the project trying to achieve?
- Who worked on it and when?
- What exact PC, ROS 2 distribution, branch, map, and configuration were used?
- What commands start the system?
- What should the user see when the setup is working?
- Where are the logs, datasets, videos, maps, and results?
- What failed, what was not completed, and what should be done next?
- What must not be changed without checking with the maintainer?

## Required metadata block

Every project `index.md` should include this table near the top:

| Field | Value |
|---|---|
| Project type | TODO: Research / Student / Temporary test / Integration / Demo |
| Status | TODO: Planned / Active / Paused / Completed / Archived |
| Start date | TODO: YYYY-MM-DD |
| End date | TODO: YYYY-MM-DD or ongoing |
| Maintainer(s) | TODO: Name(s) and contact(s) |
| Related repository | TODO: Link or internal path |
| Data location | TODO: Link or internal path |

!!! danger "Do not document secrets"

    Do not place sensitive passwords, private keys, VPN details, private Wi-Fi credentials, or access tokens in public documentation. Use protected internal storage and link to it only when appropriate.
