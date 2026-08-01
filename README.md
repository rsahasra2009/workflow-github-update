# workflow-github-update

A GitHub Actions workflow that runs once every hour, creates a file named with the
current UTC datetime stamp under the `DateTimeStamps/` directory, and pushes it back
to this repository.

## How it works

- Workflow: [.github/workflows/datetime-stamp.yml](.github/workflows/datetime-stamp.yml)
- Trigger: `schedule` (cron `0 * * * *`) and manual `workflow_dispatch`
- Each run creates `DateTimeStamps/<YYYY-MM-DDTHH-MM-SSZ>.txt` and commits it.

> Note: GitHub scheduled workflows run on a best-effort basis and can be delayed
> during periods of high load, so runs may not be exactly on the hour.
