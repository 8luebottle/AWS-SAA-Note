# Amazon SWF
> Amazon SWF helps developers build, run, and scale background jobs that have parallel or sequential steps.

- `Digital Env + Human Tasks` (Any kind of Manual interact) => SWF
  - `Human, Warehouse`  

    ![SWF Warehouse example](https://user-images.githubusercontent.com/48475824/145400570-fd73a428-5576-43b3-85fe-e8a1d2cfe82e.png)  
    Task represents invocation of various processing steps in an application which can be performed by executable code, web service call, human actions, and scripts.

- HA, Durable, PUB/SUB messaging service.

- [`3 SWF Actors`][actors]:

  ![SWF Actors](https://user-images.githubusercontent.com/48475824/145401081-5b715aaf-b64e-4cdb-8eb8-247f5ea91221.png)

  1. **Workflow Starters**:  
    An application that can initiate (start) a workflow.

  2. **Deciders**:  
    Control the flow of activity tasks in a workflow execution.
      - If something has finished(or failed) in a workflow, a Decider decides what to do next.

  3. **Activity Workers**:  
    Carry out the activity tasks.

- [`Use cases`][use-cases]:  
  - Video Encoding
  - Data Center Migration
  - Product Catalog With Human Workers

- `SWF Vs. SQS`

  |  | SWF | SQS |
  | --- | --- | --- |
  | Retention Period | up to 1 year | up to 14 days |
  | ORIENTED | Task-oriented | Message-oriented |
  | DUPLICATED | Task assign only Once ⇒ X duplicated | Need to handle duplicated message (standard) |

<!-- Labeling -->
[actors]: https://docs.aws.amazon.com/amazonswf/latest/developerguide/swf-dev-actors.html
[use-cases]: https://aws.amazon.com/swf/
