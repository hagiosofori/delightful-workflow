# Delightful workflow

### A workflow for software development I'm thinking up. Feel free to critique and recommend changes

## Influenced/inspired by

- [GitHub Flow](https://guides.github.com/introduction/flow/)
- [GitLab Flow](https://docs.gitlab.com/ee/topics/gitlab_flow.html)

## The Process

1. ### Creation of issue for desired feature

2. ### Description of desired feature in the created issue

3. ### Creation of Feature branch and pull request, detailing Design & Implementation plans
*template:*

**user experience and user interface design plan (if applicable)**
* ensure design is created for the various screen types to be supported.
* design should comprise components, screens and workflows, with animations and transitions and exact color specs.
* [Insert Link to UI/UX workflow prototype here](https://yourlinkhere.com)

**engineering and implementation plan**

*for each step*
* briefly state the step, 
* define any implementation details right under the step. 
* details can be expressed in pseudocode, but the closer to the real implementation, the better.
* when unsure about how to implement a particular feature, isolated experiments and demos can prove very helpful.
* these codesandbox experiments and demos for individual steps can be linked right under the step.
* and then the various tests that will be written for that particular implementation detail
* eg:
```
**Feature: Implement Authentication/Login system**

  ...

5. Create sign in input validation function
   - validate (string username, string password):
        handle invalid input errors
        sanitize the input
        return sanitized input

    - unit tests
         - returns correct value for correct input
         - handles invalid input well. 
            - empty username or password ...  
            - undefined, null, invalid non-alphanumeric characters, ...

 
... after all steps have been listed ...

- integration tests ... 

- end to tend tests
      - clicking the button triggers the login function
      - invalid input + login button clicked = error message showing
      - valid input + login button clicked = taken to dashboard ...
 
```
NB: don't forget; implementing the UI is part of the steps to be indicated here. details should be provided as well. pseudocode or even real code in codesandboxes are appreciated.


3.5. ### iterative revisions and reviews until all issues are ironed out, and details are firmed and validated

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
