# Delightful workflow

### A workflow for software development I'm thinking up. Feel free to critique and recommend changes

## Influenced/inspired by

- [GitHub Flow](https://guides.github.com/introduction/flow/)
- [GitLab Flow](https://docs.gitlab.com/ee/topics/gitlab_flow.html)

## The Process

1. ### Creation of issue for desired feature

2. ### Description of desired feature in the created issue

3. ### Design & Planning

- UI/UX DESIGN

  - Design of UI/UX end result (if any), including user workflow.
  - Review and iteration of UI/UX end result

- ENGINEERING DESIGN
  - Description of how desired feature will be completely implemented; logic and pseudocode, preferably. (this will be in the created issue).
  - Description of test cases to be written for the feature.
  - Description of how UI will be implemented.
  - Review and iteration of algorithm, test cases and descriptions.

4. ### Creation of feature branch, and implementation of feature

5. ### Inline documentation (with documentation auto-generation tool in the language)

6. ### Creation of merge request (also known as pull request) for code review

7. ### Code review and iterative improvement

8. ### Removal of console logs & warning messages

9. ### Building and testing of code on feature branch in testing environment.

- On successful testing

  - Pull in the master branch
  - Fix merge conflicts (if any)
  - Merge with master
  - (Master should be automatically configured on CI/CD to deploy to production environment on successful merges)

- On unsuccessful testing
  - Fix issues in feature branch, and update merge request
  - Recommence from code review stage.

10. ### Post-pushing to Production

- On successful merging

  - Delete feature branch. We're done.

- On unsuccessful merging
  - Roll back master branch, and repush to production
  - Pull master branch into feature branch
  - Run feature branch in testing. Figure out issues, and fix issues
  - Recommence from code review stage.
