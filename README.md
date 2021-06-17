# command-output-file-action

[![Action test on Ubuntu](https://github.com/GuillaumeFalourd/command-output-file-action/actions/workflows/ubuntu_test_command_output.yml/badge.svg)](https://github.com/GuillaumeFalourd/command-output-file-action/actions/workflows/ubuntu_test_command_output.yml) [![Action test on MacOS](https://github.com/GuillaumeFalourd/command-output-file-action/actions/workflows/macos_test_command_output.yml/badge.svg)](https://github.com/GuillaumeFalourd/command-output-file-action/actions/workflows/macos_test_command_output.yml) [![Action test on Windows](https://github.com/GuillaumeFalourd/command-output-file-action/actions/workflows/windows_test_command_output.yml/badge.svg)](https://github.com/GuillaumeFalourd/command-output-file-action/actions/workflows/windows_test_command_output.yml)

![title](https://user-images.githubusercontent.com/22433243/122457400-fcde6c80-cf84-11eb-8ff3-65264e80c222.png)

Github Action to generate an output file from a command execution (success or error) 📝

* * *

## 🖥 Supported OS

OS | SUPPORTED
---------- | ------------
**LINUX** | YES
**MACOS** | YES
**WINDOWS** | YES

## 📚 How to use this action?

The [`actions/checkout`](https://github.com/actions/checkout) is mandatory to use this action, as it will be necessary to access the repository files to get the output file after the action execution.

Field | Mandatory | Observation
------------ | ------------  | -------------
**command_line** | YES | ex: `ls -lha`
**output_file_name** | YES | ex: `output.txt`
**display_file_content** | NO | `YES` (default) or `NO`

_**Notes**: 

- A **command line error won't break the workflow**, but just extract the output on the file.
- You can then access the **output file** in the directory **where you ran the action**._

 * * *

### 📝 Usage example

#### WITH output file display on workflow run

```yaml
    steps:
      - uses: actions/checkout@v2.3.4
      - uses: GuillaumeFalourd/command-output-file-action@v1
        with:
          command_line: ls -lha
          output_file_name: output.txt
          display_file_content: YES # this is also the default value if not informed
```

#### WITHOUT output file display on workflow run

```yaml
    steps:
      - uses: actions/checkout@v2.3.4
      - uses: GuillaumeFalourd/command-output-file-action@v1
        with:
          command_line: ls -lha
          output_file_name: output.txt
          display_file_content: NO # YES is the default value if not informed
```

## Licensed

This repository uses the [Apache License 2.0](https://github.com/GuillaumeFalourd/aws-cliaction/blob/main/LICENSE)
