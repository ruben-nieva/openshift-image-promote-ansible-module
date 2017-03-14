# openshift-image-promote-ansible-module

This module was originally part of https://github.com/rht-labs/ansible-stacks, but it is no longer used there, so it's been spun out to it's own thing. The idea was to have an ansible module that could move images between projects, right now only with `oc tag`. Sometimes this requires you to what for the image to be built, so the module will poll at defined defaults.

# Running and Writing Units Tests

**The unit tests have the following expectations:**

* `oc` is installed on the host where the tests are running
* `oc login` has been performed with a user that can create projects and objects in those projects
* [pytest is installed](http://doc.pytest.org/en/latest/getting-started.html)
* each unit test cleans up after itself. due to async deletes in OpenShift, you may need to pause between test executions so the cluster can finish deleting resources before you try to recreate them in the test.

**To the run the tests:**
```
$ pytest tests/units
```