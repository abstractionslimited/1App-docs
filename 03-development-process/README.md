# Development Process Guide

This guide outlines the key steps required to ensure a smooth transition and successful development within the 1App `my-vodacom-mono` repository. It covers the process from branch creation to deployment, including code updates, testing, commits, peer review, and builds.

## Assumptions

- The project is already set up for development on your machine.

## Development Steps

### 1. Create a Feature Branch

1. **Create a feature branch** against the issued development subtask from the `master` branch. The branch name should follow this format:
    ```
    feature/PAPP-1234-some-development-subtask
    ```
    where `PAPP-1234-some-development-subtask` matches the description of your development subtask.

2. **Pull changes** from the remote repository to ensure your local repository is up to date:
    ```sh
    git pull origin master
    ```

3. **Checkout to your branch** to start making changes:
    ```sh
    git checkout -b feature/PAPP-1234-some-development-subtask
    ```

### 2. Update Source Code

- Make the necessary code changes, addressing the issues outlined in the ticket.
- Follow the project's coding standards. For more information, reach out to a developer on the 1App Team.

### 3. Test Changes Locally

- Test your changes locally to ensure there are no side-effects to the `master` branch code.

### 4. Commit and Push Changes

1. **Add all updated files**:
    ```sh
    git add .
    ```
    or add a specific file:
    ```sh
    git add [filename]
    ```

2. **Commit your changes** with a message prefix matching your feature branch name after the `/`:
    ```sh
    git commit -m 'PAPP-1234: Update css'
    git commit -m 'PAPP-1234: Update calculateSum function'
    ```

3. **Push your changes** to the remote repository:
    ```sh
    git push origin feature/PAPP-1234-some-development-subtask
    ```

### 5. Build and Peer Review

1. **Ensure your branch builds successfully**. Use Team City if the build does not trigger automatically after `git push`. Debug any build failures on Team City Build Logs.

2. **Create a Peer Review (PR)** pointing to the next release branch:
    ```
    feature/PAPP-1234-some-development-subtask → release/release-name
    ```

3. **Notify the 1App Team** that you have created a PR.

4. **Address PR comments** until your changes are approved by the team.

### 6. Merge and Deploy

1. Once approved, **merge your code** and run the build on Team City for QA testing. Coordinate with the Fibre team if necessary.

2. Once QA testers approve your changes, **create a pull request from `release` to `master`**.

3. **Merge the pull request** once approved.

## PR Checklist

- [ ] Code meets the acceptance criteria.
- [ ] Unit tests are done for all business components.
- [ ] Integration tests are done for the specified REST APIs.
- [ ] Build is passing.
- [ ] [Code Review Best Practices](https://roadmap.sh/best-practices/code-review)
