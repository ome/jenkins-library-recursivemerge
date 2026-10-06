
# Jenkins Library Recursive Merge

Outline of the stack involving `jenkins-library-recursivemerge`:

```

Jenkins job
    │
    │ loads
    ▼
jenkins-library-recursivemerge
    │
    │ recursiveCheckout()
    │   → checks out idr/idr.openmicroscopy.org
    │
    │ recursiveMerge()
    ▼
build-infra / recursive-merge
    │
    │ invokes
    ▼
SCC
    │
    │ examines the repository
    │ and performs the PR merges
    ▼
idr.openmicroscopy.org

```

Relevent links:

 - https://github.com/ome/jenkins-library-recursivemerge
 - https://github.com/ome/build-infra
 - https://github.com/ome/scc


In short:

 - Jenkins runs the pipeline.
 - jenkins-library-recursivemerge provides recursiveCheckout() and recursiveMerge() and orchestrates the process.
 - build-infra contains the underlying recursive-merge machinery.
 - SCC is what actually understands the repository/PR configuration and performs the merges.

See https://github.com/ome/devspace/pull/237 for example usage.

