# Delightful workflow

### A workflow for software development I'm thinking up. Feel free to critique and recommend changes

## Influenced/inspired by

- [GitHub Flow](https://guides.github.com/introduction/flow/)
- [GitLab Flow](https://docs.gitlab.com/ee/topics/gitlab_flow.html)

## The Process

1. ### Creation of issue for desired feature

2. ### Description of desired feature in the created issue

3. ### Creation of Feature branch and pull request, detailing Design & Implementation plans
[**Link to Design & Implementation planning Template**](https://github.com/hagiosofori/delightful-workflow/blob/master/plan_template.md)

*iterate over the design and implementation plan until satisfied*


4. ### implementation of feature

5. ### Inline documentation (with documentation auto-generation tool in the language)

6. ### Creation of merge request (also known as pull request) for code review

7. ### Code & Inline documentation review and iterative improvement

~8. ### Removal of console logs & warning messages~

9. ### Building and testing of code on feature branch in testing environment.

- On successful testing
  - remove console.logs and warning messages
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
