<!-- start title -->

# GitHub Action:Upload npm protos to google artifact registry

<!-- end title -->
<!-- start description -->

Uploads generated protos to google artifact registry

<!-- end description -->
<!-- start contents -->
<!-- end contents -->
<!-- start usage -->

```yaml
- uses: catalystcommunity/action-upload-protos-npm-gar@undefined
  with:
    # Google credentials json
    credentials-json: ""

    # Google cloud project id
    project-id: ""

    # NPM package name
    package-name: ""

    # Version to publish
    # Default: ${{ .github.event.release.tag_name }}
    version: ""

    # Artifact registry scope - i.e. @mycompany
    scope: ""

    # Artifact registry repository name
    # Default: npm
    repository: ""

    # Artifact registry location
    # Default: us-central1
    location: ""

    # Location of the generated protos
    # Default: build/nodejs
    proto-directory: ""
```

<!-- end usage -->
<!-- start inputs -->

| **Input**              | **Description**                           |               **Default**               | **Required** |
| :--------------------- | :---------------------------------------- | :-------------------------------------: | :----------: |
| **`credentials-json`** | Google credentials json                   |                                         |   **true**   |
| **`project-id`**       | Google cloud project id                   |                                         |   **true**   |
| **`package-name`**     | NPM package name                          |                                         |   **true**   |
| **`version`**          | Version to publish                        | `${{ .github.event.release.tag_name }}` |  **false**   |
| **`scope`**            | Artifact registry scope - i.e. @mycompany |                                         |   **true**   |
| **`repository`**       | Artifact registry repository name         |                  `npm`                  |  **false**   |
| **`location`**         | Artifact registry location                |              `us-central1`              |  **false**   |
| **`proto-directory`**  | Location of the generated protos          |             `build/nodejs`              |  **false**   |

<!-- end inputs -->
<!-- start outputs -->

| **Output**      | **Description** | **Default** | **Required** |
| :-------------- | :-------------- | ----------- | ------------ |
| `random-number` | Random number   |             |              |

<!-- end outputs -->
<!-- start examples -->

### Example usage

```yaml
on: [push]

jobs:
  hello_world_job:
    runs-on: ubuntu-latest
    name: A job to say hello
    steps:
      - uses: actions/checkout@v2
      - id: foo
        uses: actions/hello-world-composite-action@v1
        with:
          who-to-greet: "Mona the Octocat"
      - run: echo random-number ${{ steps.foo.outputs.random-number }}
        shell: bash
```

<!-- end examples -->
<!-- start [.github/ghdocs/examples/] -->
<!-- end [.github/ghdocs/examples/] -->
