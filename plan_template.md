- _[insert link to issue description along with the ID of the issue here. eg: `#1234` here](https://linktoissue.com)_
eg: 
```
[feature: sign in functionality #1234]()
```

---

**user experience and user interface design plan (if applicable)**

- [Link to UI/UX workflow prototype](https://yourlinkhere.com)
  (ensure design is created for the various screen types to be supported)
  - would be perfect if design files were stored in the same repo as code.

---

**engineering and implementation plan**

_for each step_

- briefly state the step,
- define any implementation details right under the step.
  - details can be expressed in pseudocode, but the closer to the real implementation, the better.
  - when unsure about how to implement a particular feature, isolated experiments and demos can prove very helpful.
  - these codesandbox experiments and demos for individual steps can be linked right under the step.
  - if isolating the experiment will prove difficult / incomplete, implement the experiment in a new branch, and push as part of the PR.
- then define the various tests that will be written for that particular implementation detail
  - consider the following situations when testing
    - what are all the possible inputs and outputs this code can handle/produce? test that this is the case. ie: it does what it's supposed to do, under all expected cases & edge cases.
    - performance testing
    - security testing
- eg:

```
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
            - undefined, null, invalid non-alphanumeric characters,

   ...

```


_after all the steps have been listed_

- list integration tests

- list end-to-end tests
  - security
  - stress/performance
  - functionality
