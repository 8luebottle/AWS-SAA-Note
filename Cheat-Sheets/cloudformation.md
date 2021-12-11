# AWS CloudFormation
> AWS CloudFormation lets you model, provision, and manage AWS and third-party resources by treating `infrastructure as code`.

![cloudformation](https://user-images.githubusercontent.com/48475824/145673772-64b60e0c-7762-44e3-82de-c4847bee3bed.png)

Is a way of completely `scripting your cloud environment`

- **Quick Start** is a bunch of CloudFormation templates already built by AWS SA allowing you to create complex environments very quickly.

- `automate the provisioning of resources`

- `Infrastructure as Code (IaC)`

- [`Templates`][templates]:
  - written in **JSON** or **YAML**  
    <details><summary>JSON</summary>

      ```
      {
        "AWSTemplateFormatVersion" : "version date",

        "Description" : "JSON string",

        "Metadata" : {
          template metadata
        },

        "Parameters" : {
          set of parameters
        },
        
        "Rules" : {
          set of rules
        },

        "Mappings" : {
          set of mappings
        },

        "Conditions" : {
          set of conditions
        },

        "Transform" : {
          set of transforms
        },

        "Resources" : {
          set of resources
        },
        
        "Outputs" : {
          set of outputs
        }
      }
      ```
    </details>

    <details><summary>YAML</summary>

      ```
      AWSTemplateFormatVersion: "version date"

      Description:
        String

      Metadata:
        template metadata

      Parameters:
        set of parameters

      Rules:
        set of rules

      Mappings:
        set of mappings

      Conditions:
        set of conditions

      Transform:
        set of transforms

      Resources:
        set of resources

      Outputs:
        set of outputs
      ```
    </details><br>

  - if template > 51,200 bytes (0.05MB) ⇒ must be imported into CloudFormation ⇒ via an S3 bucket.
  - `At least one resource` under resources: must be defined for a CloudFormation template to be valid.

- when CloudFormation encounters an error it will rollback with [`RollBackInProgress`][rollbackinprogress]

- **Nested Stacks** helps you break up your CloudFormation template into small reusable templates that can be composed into larger templates.

- **Conditions** are whether resources are created or properties are assigned.

<!-- Labeling -->
[templates]: https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-guide.html
[rollbackinprogress]: https://docs.aws.amazon.com/sdk-for-go/api/service/directoryservice/
