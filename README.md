# status-badge-for-tags

[![Development Deployment](https://github.com/agarthetiger/status-badge-for-tags/actions/workflows/development.yml/badge.svg?branch=main)](https://github.com/agarthetiger/status-badge-for-tags/actions/workflows/development.yml)

Demo repo for Github Actions workflows when using tags as a trigger. This repo highlights how the status badge system behaves at the time of writing, where it is not possible to get the status of the latest workflow run if that workflow is triggered by pushing a tag.

## Details

There are two workflows in this repo, one for a fictitious development deployment and one for production. The development workflow is triggered by pushing changes in the `terraform/` folder, and runs automatically on push to main.

The production workflow is triggered by tagging a commit on the main branch, or by manually running the workflow via `workflow_dispatch`.

The behaviour observed is that it's not possible to get a status badge to reflect the last production workflow run. Even though the status badge urls allow for selecting a workflow file by name, as well as the branch and various events, it is not possible to get the status for the workflows triggered from pushing a tag.
