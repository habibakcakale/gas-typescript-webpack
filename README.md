# Google AppScript with typescript and webpack

This is an example code for writing Google Apps Script in TypeScript and building with webpack.

## Requirements

- Node
- [clasp](https://github.com/google/clasp)

Then enable the Google Apps Script API: https://script.google.com/home/usersettings
![Enable Apps Script API](https://user-images.githubusercontent.com/744973/54870967-a9135780-4d6a-11e9-991c-9f57a508bdf0.gif)

## Project Settings File (`.clasp.json`)

When running `clone` or `create`, a file named `.clasp.json` is created in the current directory to describe `clasp`'s configuration for the current project. Example `.clasp.json`:

```json
{
  "scriptId": "",
  "rootDir": "build/",
  "projectId": "project-id-xxxxxxxxxxxxxxxxxxx",
  "fileExtension": "ts",
  "filePushOrder": ["file1.ts", "file2.ts"]
}
```

The following configuration values can be used:

### `scriptId` (required)

Specifies the id of the Google Script project that clasp will target.

1. Open script url.
1. File > Project properties > Script ID

### `rootDir` (optional)

Specifies the **local** directory in which clasp will store your project files. If not specified, clasp will default to the current directory.

### `projectId` (optional)

Specifies the id of the Google Cloud Platform project that clasp will target.
You must [associate Google Script project with Google Cloud Platform](https://github.com/google/clasp/blob/master/docs/run.md#setup-instructions) beforehand.

1. Run `clasp open`.
1. Click `Resources > Cloud Platform project...`.
1. Specify the project ID `project-id-xxxxxxxxxxxxxxxxxxx`.

Even if you do not set this manually, clasp will ask this via a prompt to you at the required time.

### `fileExtension` (optional)

Specifies the file extension for **local** script files in your Apps Script project.

### `filePushOrder` (optional)

Specifies the files that should be pushed first, useful for scripts that rely on order of execution. All other files are pushed after this list of files.
