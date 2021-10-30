## Notes
- You may notice build succeeded, but each of the test jobs failed. That's because the build artifacts created in build aren't available to the test job. Each job executes in a fresh instance of the virtual environment. 

- So what do we do when we need the work product of one job in another? We can use the built-in artifact storage to save artifacts created from one job to be used in another job within the same workflow.

- Artifacts allow you to persist data after a job has completed, and share that data with another job in the same workflow. An artifact is a file or collection of files produced during a workflow run.

- To upload artifacts to the artifact storage, we can use an action built by GitHub: actions/upload-artifacts.

- Each job runs in its own virtual environment, so although we've pushed our artifacts to storage, the test job needs to retrieve them.

- Similar to the upload action to send artifacts to the storage, we'll use another action built by GitHub to download these previously uploaded artifacts from the build job: actions/download-artifact

- workflows can be configured to run:
Using events from GitHub
At a scheduled time
When an event outside of GitHub occurs
