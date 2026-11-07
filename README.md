# TrainCost external consumer validation

This public repository tests the report-only TrainCost CI candidate from a
different repository. It contains synthetic configurations and a verification
workflow, not a copy of the Action implementation. No GPU training, model/data
downloads, cloud credentials, or PR comments are used.

The root and package Actions are pinned to
`Pig30nidaE/TrainCost@28b4c541ab98a840a814f6bed8d3b205ece3d4ca`.
This is a candidate SHA, not a published release tag.

The baseline uses one epoch and a hypothetical RTX3060 hourly rate of $1. A test
PR changes only the epoch count to three and adds valid/invalid native HF cases.
The workflow checks complete, partial, and error states; actual output paths;
false comment outputs; report/Step Summary equality; and unsafe-output rejection.
Missing base configs use explicit defaults, not measured savings.

Keep the validation PR unmerged. Its artifact records repository identities and
whether the head is a real fork. An ordinary branch PR here proves external Action
consumption, not real fork permissions. Only a separate fork PR can prove that gate.

Do not add secrets or register a self-hosted runner. Use the GitHub-hosted Linux
runner and read-only contents permission. This repository does not authorize a
release, tag push, or merge in the source project.

Source and implementation evidence: [TrainCost](https://github.com/Pig30nidaE/TrainCost).
The workflow and synthetic fixture code retain the project's MIT license.
