# flow disable

Disables specified Microsoft Flow

## Usage

```sh
flow disable [options]
```

## Options

Option|Description
------|-----------
`--help`|output usage information
`-n, --name <name>`|The name of the Microsoft Flow to disable
`-e, --environment <environment>`|The name of the environment for which to disable Flow
`--asAdmin`|Set, to disable the Flow as admin
`-o, --output [output]`|Output type. `json|text`. Default `text`
`--verbose`|Runs command with verbose logging
`--debug`|Runs command with debug logging

## Remarks

!!! attention
    This command is based on an API that is currently in preview and is subject to change once the API reached general availability.

By default, the command will try to disable Microsoft Flows you own. If you want to disable Flow owned by another user, use the `asAdmin` flag.

If the environment with the name you specified doesn't exist, you will get the `Access to the environment 'xyz' is denied.` error.

If the Microsoft Flow with the name you specified doesn't exist, you will get the `The caller with object id 'abc' does not have permission for connection 'xyz' under Api 'shared_logicflows'.` error. If you try to disable a non-existing flow as admin, you will get the `Could not find flow 'xyz'.` error.

## Examples

Disables Microsoft Flow owned by the currently signed-in user

```sh
flow disable --environment Default-d87a7535-dd31-4437-bfe1-95340acd55c5 --name 3989cb59-ce1a-4a5c-bb78-257c5c39381d
```

Disables Microsoft Flow owned by another user

```sh
flow disable --environment Default-d87a7535-dd31-4437-bfe1-95340acd55c5 --name 3989cb59-ce1a-4a5c-bb78-257c5c39381d --asAdmin
```