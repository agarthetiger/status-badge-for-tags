# status-badge-for-tags

[![Development Deployment](https://github.com/agarthetiger/status-badge-for-tags/actions/workflows/development.yml/badge.svg?branch=main)](https://github.com/agarthetiger/status-badge-for-tags/actions/workflows/development.yml) [![Production Deployment](https://github.com/agarthetiger/status-badge-for-tags/actions/workflows/production.yml/badge.svg?branch=main)](https://github.com/agarthetiger/status-badge-for-tags/actions/workflows/production.yml)

Demo repo for Github Actions workflows when using tags as a trigger. This repo highlights how the status badge system behaves at the time of writing, where it is not possible to get the status of the latest workflow run if that workflow is triggered by pushing a tag.

## Details

There are two workflows in this repo, one for a fictitious development deployment and one for production. The development workflow is triggered by pushing changes in the `terraform/` folder, and runs automatically on push to main.

The production workflow is triggered by tagging a commit on the main branch, or by manually running the workflow via `workflow_dispatch`.

## Expectation

My expectation is that it is possible to display markdown for a badge which will reflect the most recent run of the "Production Deployment" `production.yml` workflow. Either that or it should be possible to display the status of this workflow when triggered by the push of a matching tag, as per the `on:` section in the workflow file.

## Actual behaviour

At the time of writing, the behaviour observed is that it's not possible to get a status badge to reflect the last production workflow run. Even though the status badge urls allow for selecting a workflow file by name, as well as the branch and various events, it is not possible to get the status for the workflows triggered from pushing a tag.

### Status Badges

The first production deployment was triggered by `workflow_dispatch` and cancelled. Subsequent production deployments have been triggered by tagging the code on main and pushing with tags.

* [![Production Deployment](https://github.com/agarthetiger/status-badge-for-tags/actions/workflows/production.yml/badge.svg)](https://github.com/agarthetiger/status-badge-for-tags/actions/workflows/production.yml) Branch: Default, Event: Default
* [![Production Deployment](https://github.com/agarthetiger/status-badge-for-tags/actions/workflows/production.yml/badge.svg?branch=main)](https://github.com/agarthetiger/status-badge-for-tags/actions/workflows/production.yml) Branch: main, Event: Default
* [![Production Deployment](https://github.com/agarthetiger/status-badge-for-tags/actions/workflows/production.yml/badge.svg?branch=main&event=push)](https://github.com/agarthetiger/status-badge-for-tags/actions/workflows/production.yml) Branch: main, Event: Push
* [![Production Deployment](https://github.com/agarthetiger/status-badge-for-tags/actions/workflows/production.yml/badge.svg?branch=main&event=workflow_run)](https://github.com/agarthetiger/status-badge-for-tags/actions/workflows/production.yml) Branch: main, Event: workflow_run
