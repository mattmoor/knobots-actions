# Welcome to knobots-actions

This repository contains a number of github actions, which perform routine
maintenance tasks for a variety of repositories, mostly for the knative org.

To add a repository here, there are two requirements:
1. Add an entry to `repos.yaml` containing an entry like this:

   ```yaml
    - # name is the repository to operate on, think: https://github.com/{name}.git
      name: 'knative/pkg'

      # meta-organization is the github organization from which to sync Github
      # actions, think: https://github.com/{meta-organization}/.github
      # Actions are pulled from the workflow-templates directory.
      meta-organization: 'knative'

      # repository is the name of the repository within the organization.
      repository: 'pkg'

      # channel is the channel on knative.slack.com to post when these actions fail.
      # These can be a direct-message to a username if prefixed with `@`
      channel: 'serving-api'

      # The list of users to which the PR should be `/assign` (only matters for Prow)
      assignees: n3wscott vagababov
   ```

2. A fork under `github.com/mattmoor/{repository}.git`


Repos can also optionally exclude certain jobs by adding their name to the appropriate `{foo}-exclude.yaml` file.