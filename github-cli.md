# Github CLI Cheatsheet
-----------------------------------------------------------------------------
*This file explains how to use **GitHub CLI** to interact with GitHub directly from the command line.*

## Prerequisites
Before using GitHub CLI, you must install it and authenticate your GitHub account.

### Installation
- **Linux**:
  ```bash
  sudo apt install gh  # Debian/Ubuntu
  sudo dnf install gh  # Fedora
  ```
-----------------------

| **Command**                                      | **Description**                                                       | **Example Usage**                                                                                                                                 |
|--------------------------------------------------|-----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| `gh auth login`                                  | Authenticate with your GitHub account                                  | `gh auth login`                                                                                                                                   |
| `gh auth status`                                 | Check the authentication status                                       | `gh auth status`                                                                                                                                  |
| `gh repo clone <username>/<repository>`          | Clone a GitHub repository                                             | `gh repo clone octocat/hello-world`                                                                                                               |
| `gh repo create <repository_name>`               | Create a new GitHub repository                                        | `gh repo create new-repo --public`                                                                                                                |
| `gh repo list`                                   | List repositories from your GitHub account                             | `gh repo list`                                                                                                                                   |
| `gh repo view`                                   | View repository information                                           | `gh repo view octocat/hello-world --web`                                                                                                          |
| `gh pr create --base <branch> --head <branch>`    | Create a new pull request                                              | `gh pr create --base main --head feature/new-feature --title "Add New Feature" --body "Details"`                                                |
| `gh pr list`                                     | List open pull requests in a repository                                | `gh pr list`                                                                                                                                     |
| `gh pr view <pr_number>`                         | View a pull request by number                                          | `gh pr view 5`                                                                                                                                   |
| `gh pr merge <pr_number>`                        | Merge a pull request into the base branch                              | `gh pr merge 5`                                                                                                                                  |
| `gh issue create --title "<title>" --body "<body>"` | Create a new issue in the repository                                  | `gh issue create --title "Bug Report" --body "Description of issue"`                                                                              |
| `gh issue list`                                  | List open issues in a repository                                       | `gh issue list`                                                                                                                                  |
| `gh issue view <issue_number>`                   | View a specific issue by number                                        | `gh issue view 1`                                                                                                                                 |
| `gh repo delete <repository_name>`               | Delete a repository from GitHub                                        | `gh repo delete my-repo`                                                                                                                         |
| `gh pr checkout <pr_number>`                     | Checkout a pull request locally                                        | `gh pr checkout 5`                                                                                                                                 |
| `gh pr status`                                   | View the status of pull requests                                      | `gh pr status`                                                                                                                                  |
| `gh repo rename <new_name>`                      | Rename a repository                                                    | `gh repo rename new-repo-name`                                                                                                                   |
| `gh repo fork`                                   | Fork a repository                                                      | `gh repo fork octocat/hello-world`                                                                                                               |
| `gh pr ready`                                    | Mark a pull request as ready for review                               | `gh pr ready`                                                                                                                                   |
| `gh pr comment <pr_number> --body "<comment>"`    | Comment on a pull request                                             | `gh pr comment 5 --body "Looks good to me!"`                                                                                                    |
| `gh --version`                                   | Display the current version of GitHub CLI                              | `gh --version`                                                                                                                                  |
| `gh help`                                        | Display help for any command                                           | `gh help`                                                                                                                                       |
                                                                                                                                                             

------------------
### Conclusion : 

GitHub CLI (gh) lets you manage repositories, pull requests, issues, and more directly from the command line, simplifying many common GitHub tasks.

This table covers the main commands seen so far, but there are many other options and subcommands that can be explored via gh help for more details.



