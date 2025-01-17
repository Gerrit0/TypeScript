# getDirectoryToWatchFailedLookupLocation

Determines whether to watch given failed lookup location (file that didnt exist) when resolving module.
It also determines the directory to watch and whether to watch it recursively or not.

## Testing for Dos root: c:/

## RootDirForResolution: c:/

Root: c:

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               | c:                                                                                             | true      |
| c:/dir/somefile.d.ts                                                                           | c:/dir                                                                                         | true      |
| c:/dir/subdir/somefile.d.ts                                                                    | c:/dir                                                                                         | true      |
| c:/folderAtRoot/somefile.d.ts                                                                  | c:/folderAtRoot                                                                                | true      |
| c:/folderAtRoot/dir/somefile.d.ts                                                              | c:/folderAtRoot                                                                                | true      |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       | c:/folderAtRoot                                                                                | true      |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          | c:/folderAtRoot                                                                                | true      |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      | c:/folderAtRoot                                                                                | true      |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               | c:/folderAtRoot                                                                                | true      |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  | c:/folderAtRoot                                                                                | true      |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              | c:/folderAtRoot                                                                                | true      |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       | c:/folderAtRoot                                                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          | c:/folderAtRoot                                                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      | c:/folderAtRoot                                                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               | c:/folderAtRoot                                                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  | c:/folderAtRoot                                                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              | c:/folderAtRoot                                                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       | c:/folderAtRoot                                                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          | c:/folderAtRoot                                                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      | c:/folderAtRoot                                                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               | c:/folderAtRoot                                                                                | true      |
| c:/users/somefile.d.ts                                                                         | c:/users                                                                                       | true      |
| c:/users/dir/somefile.d.ts                                                                     | c:/users                                                                                       | true      |
| c:/users/dir/subdir/somefile.d.ts                                                              | c:/users                                                                                       | true      |
| c:/users/username/somefile.d.ts                                                                | c:/users                                                                                       | true      |
| c:/users/username/dir/somefile.d.ts                                                            | c:/users                                                                                       | true      |
| c:/users/username/dir/subdir/somefile.d.ts                                                     | c:/users                                                                                       | true      |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   | c:/users                                                                                       | true      |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               | c:/users                                                                                       | true      |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        | c:/users                                                                                       | true      |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           | c:/users                                                                                       | true      |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       | c:/users                                                                                       | true      |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                | c:/users                                                                                       | true      |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   | c:/users                                                                                       | true      |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               | c:/users                                                                                       | true      |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        | c:/users                                                                                       | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           | c:/users                                                                                       | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       | c:/users                                                                                       | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                | c:/users                                                                                       | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   | c:/users                                                                                       | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               | c:/users                                                                                       | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        | c:/users                                                                                       | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           | c:/users                                                                                       | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       | c:/users                                                                                       | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts | c:/users                                                                                       | true      |
| c:/user/somefile.d.ts                                                                          | c:/user                                                                                        | true      |
| c:/user/dir/somefile.d.ts                                                                      | c:/user                                                                                        | true      |
| c:/user/dir/subdir/somefile.d.ts                                                               | c:/user                                                                                        | true      |
| c:/user/username/somefile.d.ts                                                                 | c:/user                                                                                        | true      |
| c:/user/username/dir/somefile.d.ts                                                             | c:/user                                                                                        | true      |
| c:/user/username/dir/subdir/somefile.d.ts                                                      | c:/user                                                                                        | true      |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    | c:/user                                                                                        | true      |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                | c:/user                                                                                        | true      |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         | c:/user                                                                                        | true      |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            | c:/user                                                                                        | true      |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        | c:/user                                                                                        | true      |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 | c:/user                                                                                        | true      |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    | c:/user                                                                                        | true      |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                | c:/user                                                                                        | true      |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         | c:/user                                                                                        | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            | c:/user                                                                                        | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        | c:/user                                                                                        | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 | c:/user                                                                                        | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    | c:/user                                                                                        | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                | c:/user                                                                                        | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         | c:/user                                                                                        | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            | c:/user                                                                                        | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        | c:/user                                                                                        | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts | c:/user                                                                                        | true      |

## RootDirForResolution: c:/folderAtRoot

Root: c:/folderAtRoot

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  | c:/folderAtRoot                                                                                | true      |
| c:/folderAtRoot/dir/somefile.d.ts                                                              | c:/folderAtRoot/dir                                                                            | true      |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       | c:/folderAtRoot/dir                                                                            | true      |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          | c:/folderAtRoot/folder1                                                                        | true      |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      | c:/folderAtRoot/folder1                                                                        | true      |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               | c:/folderAtRoot/folder1                                                                        | true      |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  | c:/folderAtRoot/folder1                                                                        | true      |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              | c:/folderAtRoot/folder1                                                                        | true      |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       | c:/folderAtRoot/folder1                                                                        | true      |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          | c:/folderAtRoot/folder1                                                                        | true      |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      | c:/folderAtRoot/folder1                                                                        | true      |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               | c:/folderAtRoot/folder1                                                                        | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  | c:/folderAtRoot/folder1                                                                        | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              | c:/folderAtRoot/folder1                                                                        | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       | c:/folderAtRoot/folder1                                                                        | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          | c:/folderAtRoot/folder1                                                                        | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      | c:/folderAtRoot/folder1                                                                        | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               | c:/folderAtRoot/folder1                                                                        | true      |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                |                                                                                                |           |
| c:/users/username/dir/somefile.d.ts                                                            |                                                                                                |           |
| c:/users/username/dir/subdir/somefile.d.ts                                                     |                                                                                                |           |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      |                                                                                                |           |
| c:/user/dir/subdir/somefile.d.ts                                                               |                                                                                                |           |
| c:/user/username/somefile.d.ts                                                                 |                                                                                                |           |
| c:/user/username/dir/somefile.d.ts                                                             |                                                                                                |           |
| c:/user/username/dir/subdir/somefile.d.ts                                                      |                                                                                                |           |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |

## RootDirForResolution: c:/folderAtRoot/folder1

Root: c:/folderAtRoot/folder1

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              |                                                                                                |           |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          | c:/folderAtRoot/folder1                                                                        | true      |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      | c:/folderAtRoot/folder1/dir                                                                    | true      |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               | c:/folderAtRoot/folder1/dir                                                                    | true      |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  | c:/folderAtRoot/folder1/folder2                                                                | true      |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              | c:/folderAtRoot/folder1/folder2                                                                | true      |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       | c:/folderAtRoot/folder1/folder2                                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          | c:/folderAtRoot/folder1/folder2                                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      | c:/folderAtRoot/folder1/folder2                                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               | c:/folderAtRoot/folder1/folder2                                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  | c:/folderAtRoot/folder1/folder2                                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              | c:/folderAtRoot/folder1/folder2                                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       | c:/folderAtRoot/folder1/folder2                                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          | c:/folderAtRoot/folder1/folder2                                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      | c:/folderAtRoot/folder1/folder2                                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               | c:/folderAtRoot/folder1/folder2                                                                | true      |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                |                                                                                                |           |
| c:/users/username/dir/somefile.d.ts                                                            |                                                                                                |           |
| c:/users/username/dir/subdir/somefile.d.ts                                                     |                                                                                                |           |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      |                                                                                                |           |
| c:/user/dir/subdir/somefile.d.ts                                                               |                                                                                                |           |
| c:/user/username/somefile.d.ts                                                                 |                                                                                                |           |
| c:/user/username/dir/somefile.d.ts                                                             |                                                                                                |           |
| c:/user/username/dir/subdir/somefile.d.ts                                                      |                                                                                                |           |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |

## RootDirForResolution: c:/folderAtRoot/folder1/folder2

Root: c:/folderAtRoot/folder1/folder2

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              |                                                                                                |           |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          | c:/folderAtRoot/folder1                                                                        | false     |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      | c:/folderAtRoot/folder1/dir                                                                    | true      |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               | c:/folderAtRoot/folder1/dir                                                                    | true      |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  | c:/folderAtRoot/folder1/folder2                                                                | true      |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              | c:/folderAtRoot/folder1/folder2/dir                                                            | true      |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       | c:/folderAtRoot/folder1/folder2/dir                                                            | true      |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          | c:/folderAtRoot/folder1/folder2/folder3                                                        | true      |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      | c:/folderAtRoot/folder1/folder2/folder3                                                        | true      |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               | c:/folderAtRoot/folder1/folder2/folder3                                                        | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  | c:/folderAtRoot/folder1/folder2/folder3                                                        | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              | c:/folderAtRoot/folder1/folder2/folder3                                                        | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       | c:/folderAtRoot/folder1/folder2/folder3                                                        | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          | c:/folderAtRoot/folder1/folder2/folder3                                                        | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      | c:/folderAtRoot/folder1/folder2/folder3                                                        | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               | c:/folderAtRoot/folder1/folder2/folder3                                                        | true      |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                |                                                                                                |           |
| c:/users/username/dir/somefile.d.ts                                                            |                                                                                                |           |
| c:/users/username/dir/subdir/somefile.d.ts                                                     |                                                                                                |           |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      |                                                                                                |           |
| c:/user/dir/subdir/somefile.d.ts                                                               |                                                                                                |           |
| c:/user/username/somefile.d.ts                                                                 |                                                                                                |           |
| c:/user/username/dir/somefile.d.ts                                                             |                                                                                                |           |
| c:/user/username/dir/subdir/somefile.d.ts                                                      |                                                                                                |           |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |

## RootDirForResolution: c:/folderAtRoot/folder1/folder2/folder3

Root: c:/folderAtRoot/folder1/folder2/folder3

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              |                                                                                                |           |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          | c:/folderAtRoot/folder1                                                                        | false     |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      | c:/folderAtRoot/folder1/dir                                                                    | true      |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               | c:/folderAtRoot/folder1/dir                                                                    | true      |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  | c:/folderAtRoot/folder1/folder2                                                                | false     |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              | c:/folderAtRoot/folder1/folder2/dir                                                            | true      |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       | c:/folderAtRoot/folder1/folder2/dir                                                            | true      |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          | c:/folderAtRoot/folder1/folder2/folder3                                                        | true      |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      | c:/folderAtRoot/folder1/folder2/folder3/dir                                                    | true      |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               | c:/folderAtRoot/folder1/folder2/folder3/dir                                                    | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  | c:/folderAtRoot/folder1/folder2/folder3/folder4                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              | c:/folderAtRoot/folder1/folder2/folder3/folder4                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       | c:/folderAtRoot/folder1/folder2/folder3/folder4                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          | c:/folderAtRoot/folder1/folder2/folder3/folder4                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      | c:/folderAtRoot/folder1/folder2/folder3/folder4                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               | c:/folderAtRoot/folder1/folder2/folder3/folder4                                                | true      |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                |                                                                                                |           |
| c:/users/username/dir/somefile.d.ts                                                            |                                                                                                |           |
| c:/users/username/dir/subdir/somefile.d.ts                                                     |                                                                                                |           |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      |                                                                                                |           |
| c:/user/dir/subdir/somefile.d.ts                                                               |                                                                                                |           |
| c:/user/username/somefile.d.ts                                                                 |                                                                                                |           |
| c:/user/username/dir/somefile.d.ts                                                             |                                                                                                |           |
| c:/user/username/dir/subdir/somefile.d.ts                                                      |                                                                                                |           |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |

## RootDirForResolution: c:/folderAtRoot/folder1/folder2/folder3/folder4

Root: c:/folderAtRoot/folder1/folder2/folder3/folder4

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              |                                                                                                |           |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          | c:/folderAtRoot/folder1                                                                        | false     |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      | c:/folderAtRoot/folder1/dir                                                                    | true      |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               | c:/folderAtRoot/folder1/dir                                                                    | true      |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  | c:/folderAtRoot/folder1/folder2                                                                | false     |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              | c:/folderAtRoot/folder1/folder2/dir                                                            | true      |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       | c:/folderAtRoot/folder1/folder2/dir                                                            | true      |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          | c:/folderAtRoot/folder1/folder2/folder3                                                        | false     |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      | c:/folderAtRoot/folder1/folder2/folder3/dir                                                    | true      |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               | c:/folderAtRoot/folder1/folder2/folder3/dir                                                    | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  | c:/folderAtRoot/folder1/folder2/folder3/folder4                                                | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              | c:/folderAtRoot/folder1/folder2/folder3/folder4/dir                                            | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       | c:/folderAtRoot/folder1/folder2/folder3/folder4/dir                                            | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          | c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5                                        | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      | c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5                                        | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               | c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5                                        | true      |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                |                                                                                                |           |
| c:/users/username/dir/somefile.d.ts                                                            |                                                                                                |           |
| c:/users/username/dir/subdir/somefile.d.ts                                                     |                                                                                                |           |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      |                                                                                                |           |
| c:/user/dir/subdir/somefile.d.ts                                                               |                                                                                                |           |
| c:/user/username/somefile.d.ts                                                                 |                                                                                                |           |
| c:/user/username/dir/somefile.d.ts                                                             |                                                                                                |           |
| c:/user/username/dir/subdir/somefile.d.ts                                                      |                                                                                                |           |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |

## RootDirForResolution: c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5

Root: c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              |                                                                                                |           |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          | c:/folderAtRoot/folder1                                                                        | false     |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      | c:/folderAtRoot/folder1/dir                                                                    | true      |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               | c:/folderAtRoot/folder1/dir                                                                    | true      |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  | c:/folderAtRoot/folder1/folder2                                                                | false     |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              | c:/folderAtRoot/folder1/folder2/dir                                                            | true      |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       | c:/folderAtRoot/folder1/folder2/dir                                                            | true      |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          | c:/folderAtRoot/folder1/folder2/folder3                                                        | false     |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      | c:/folderAtRoot/folder1/folder2/folder3/dir                                                    | true      |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               | c:/folderAtRoot/folder1/folder2/folder3/dir                                                    | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  | c:/folderAtRoot/folder1/folder2/folder3/folder4                                                | false     |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              | c:/folderAtRoot/folder1/folder2/folder3/folder4/dir                                            | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       | c:/folderAtRoot/folder1/folder2/folder3/folder4/dir                                            | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          | c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5                                        | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      | c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir                                    | true      |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               | c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir                                    | true      |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                |                                                                                                |           |
| c:/users/username/dir/somefile.d.ts                                                            |                                                                                                |           |
| c:/users/username/dir/subdir/somefile.d.ts                                                     |                                                                                                |           |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      |                                                                                                |           |
| c:/user/dir/subdir/somefile.d.ts                                                               |                                                                                                |           |
| c:/user/username/somefile.d.ts                                                                 |                                                                                                |           |
| c:/user/username/dir/somefile.d.ts                                                             |                                                                                                |           |
| c:/user/username/dir/subdir/somefile.d.ts                                                      |                                                                                                |           |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |

## RootDirForResolution: c:/users

Root: c:/users

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              |                                                                                                |           |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               |                                                                                                |           |
| c:/users/somefile.d.ts                                                                         | c:/users                                                                                       | true      |
| c:/users/dir/somefile.d.ts                                                                     | c:/users/dir                                                                                   | true      |
| c:/users/dir/subdir/somefile.d.ts                                                              | c:/users/dir                                                                                   | true      |
| c:/users/username/somefile.d.ts                                                                | c:/users/username                                                                              | true      |
| c:/users/username/dir/somefile.d.ts                                                            | c:/users/username                                                                              | true      |
| c:/users/username/dir/subdir/somefile.d.ts                                                     | c:/users/username                                                                              | true      |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   | c:/users/username                                                                              | true      |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               | c:/users/username                                                                              | true      |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        | c:/users/username                                                                              | true      |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           | c:/users/username                                                                              | true      |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       | c:/users/username                                                                              | true      |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                | c:/users/username                                                                              | true      |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   | c:/users/username                                                                              | true      |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               | c:/users/username                                                                              | true      |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        | c:/users/username                                                                              | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           | c:/users/username                                                                              | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       | c:/users/username                                                                              | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                | c:/users/username                                                                              | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   | c:/users/username                                                                              | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               | c:/users/username                                                                              | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        | c:/users/username                                                                              | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           | c:/users/username                                                                              | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       | c:/users/username                                                                              | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts | c:/users/username                                                                              | true      |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      |                                                                                                |           |
| c:/user/dir/subdir/somefile.d.ts                                                               |                                                                                                |           |
| c:/user/username/somefile.d.ts                                                                 |                                                                                                |           |
| c:/user/username/dir/somefile.d.ts                                                             |                                                                                                |           |
| c:/user/username/dir/subdir/somefile.d.ts                                                      |                                                                                                |           |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |

## RootDirForResolution: c:/users/username

Root: c:/users/username

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              |                                                                                                |           |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               |                                                                                                |           |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                | c:/users/username                                                                              | true      |
| c:/users/username/dir/somefile.d.ts                                                            | c:/users/username/dir                                                                          | true      |
| c:/users/username/dir/subdir/somefile.d.ts                                                     | c:/users/username/dir                                                                          | true      |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   | c:/users/username/folderAtRoot                                                                 | true      |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               | c:/users/username/folderAtRoot                                                                 | true      |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        | c:/users/username/folderAtRoot                                                                 | true      |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           | c:/users/username/folderAtRoot                                                                 | true      |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       | c:/users/username/folderAtRoot                                                                 | true      |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                | c:/users/username/folderAtRoot                                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   | c:/users/username/folderAtRoot                                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               | c:/users/username/folderAtRoot                                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        | c:/users/username/folderAtRoot                                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           | c:/users/username/folderAtRoot                                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       | c:/users/username/folderAtRoot                                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                | c:/users/username/folderAtRoot                                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   | c:/users/username/folderAtRoot                                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               | c:/users/username/folderAtRoot                                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        | c:/users/username/folderAtRoot                                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           | c:/users/username/folderAtRoot                                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       | c:/users/username/folderAtRoot                                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts | c:/users/username/folderAtRoot                                                                 | true      |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      |                                                                                                |           |
| c:/user/dir/subdir/somefile.d.ts                                                               |                                                                                                |           |
| c:/user/username/somefile.d.ts                                                                 |                                                                                                |           |
| c:/user/username/dir/somefile.d.ts                                                             |                                                                                                |           |
| c:/user/username/dir/subdir/somefile.d.ts                                                      |                                                                                                |           |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |

## RootDirForResolution: c:/users/username/folderAtRoot

Root: c:/users/username/folderAtRoot

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              |                                                                                                |           |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               |                                                                                                |           |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                |                                                                                                |           |
| c:/users/username/dir/somefile.d.ts                                                            |                                                                                                |           |
| c:/users/username/dir/subdir/somefile.d.ts                                                     |                                                                                                |           |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   | c:/users/username/folderAtRoot                                                                 | true      |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               | c:/users/username/folderAtRoot/dir                                                             | true      |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        | c:/users/username/folderAtRoot/dir                                                             | true      |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           | c:/users/username/folderAtRoot/folder1                                                         | true      |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       | c:/users/username/folderAtRoot/folder1                                                         | true      |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                | c:/users/username/folderAtRoot/folder1                                                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   | c:/users/username/folderAtRoot/folder1                                                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               | c:/users/username/folderAtRoot/folder1                                                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        | c:/users/username/folderAtRoot/folder1                                                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           | c:/users/username/folderAtRoot/folder1                                                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       | c:/users/username/folderAtRoot/folder1                                                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                | c:/users/username/folderAtRoot/folder1                                                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   | c:/users/username/folderAtRoot/folder1                                                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               | c:/users/username/folderAtRoot/folder1                                                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        | c:/users/username/folderAtRoot/folder1                                                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           | c:/users/username/folderAtRoot/folder1                                                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       | c:/users/username/folderAtRoot/folder1                                                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts | c:/users/username/folderAtRoot/folder1                                                         | true      |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      |                                                                                                |           |
| c:/user/dir/subdir/somefile.d.ts                                                               |                                                                                                |           |
| c:/user/username/somefile.d.ts                                                                 |                                                                                                |           |
| c:/user/username/dir/somefile.d.ts                                                             |                                                                                                |           |
| c:/user/username/dir/subdir/somefile.d.ts                                                      |                                                                                                |           |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |

## RootDirForResolution: c:/users/username/folderAtRoot/folder1

Root: c:/users/username/folderAtRoot/folder1

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              |                                                                                                |           |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               |                                                                                                |           |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                |                                                                                                |           |
| c:/users/username/dir/somefile.d.ts                                                            |                                                                                                |           |
| c:/users/username/dir/subdir/somefile.d.ts                                                     |                                                                                                |           |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           | c:/users/username/folderAtRoot/folder1                                                         | true      |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       | c:/users/username/folderAtRoot/folder1/dir                                                     | true      |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                | c:/users/username/folderAtRoot/folder1/dir                                                     | true      |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   | c:/users/username/folderAtRoot/folder1/folder2                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               | c:/users/username/folderAtRoot/folder1/folder2                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        | c:/users/username/folderAtRoot/folder1/folder2                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           | c:/users/username/folderAtRoot/folder1/folder2                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       | c:/users/username/folderAtRoot/folder1/folder2                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                | c:/users/username/folderAtRoot/folder1/folder2                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   | c:/users/username/folderAtRoot/folder1/folder2                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               | c:/users/username/folderAtRoot/folder1/folder2                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        | c:/users/username/folderAtRoot/folder1/folder2                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           | c:/users/username/folderAtRoot/folder1/folder2                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       | c:/users/username/folderAtRoot/folder1/folder2                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts | c:/users/username/folderAtRoot/folder1/folder2                                                 | true      |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      |                                                                                                |           |
| c:/user/dir/subdir/somefile.d.ts                                                               |                                                                                                |           |
| c:/user/username/somefile.d.ts                                                                 |                                                                                                |           |
| c:/user/username/dir/somefile.d.ts                                                             |                                                                                                |           |
| c:/user/username/dir/subdir/somefile.d.ts                                                      |                                                                                                |           |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |

## RootDirForResolution: c:/users/username/folderAtRoot/folder1/folder2

Root: c:/users/username/folderAtRoot/folder1/folder2

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              |                                                                                                |           |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               |                                                                                                |           |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                |                                                                                                |           |
| c:/users/username/dir/somefile.d.ts                                                            |                                                                                                |           |
| c:/users/username/dir/subdir/somefile.d.ts                                                     |                                                                                                |           |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           | c:/users/username/folderAtRoot/folder1                                                         | false     |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       | c:/users/username/folderAtRoot/folder1/dir                                                     | true      |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                | c:/users/username/folderAtRoot/folder1/dir                                                     | true      |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   | c:/users/username/folderAtRoot/folder1/folder2                                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               | c:/users/username/folderAtRoot/folder1/folder2/dir                                             | true      |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        | c:/users/username/folderAtRoot/folder1/folder2/dir                                             | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           | c:/users/username/folderAtRoot/folder1/folder2/folder3                                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       | c:/users/username/folderAtRoot/folder1/folder2/folder3                                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                | c:/users/username/folderAtRoot/folder1/folder2/folder3                                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   | c:/users/username/folderAtRoot/folder1/folder2/folder3                                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               | c:/users/username/folderAtRoot/folder1/folder2/folder3                                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        | c:/users/username/folderAtRoot/folder1/folder2/folder3                                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           | c:/users/username/folderAtRoot/folder1/folder2/folder3                                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       | c:/users/username/folderAtRoot/folder1/folder2/folder3                                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts | c:/users/username/folderAtRoot/folder1/folder2/folder3                                         | true      |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      |                                                                                                |           |
| c:/user/dir/subdir/somefile.d.ts                                                               |                                                                                                |           |
| c:/user/username/somefile.d.ts                                                                 |                                                                                                |           |
| c:/user/username/dir/somefile.d.ts                                                             |                                                                                                |           |
| c:/user/username/dir/subdir/somefile.d.ts                                                      |                                                                                                |           |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |

## RootDirForResolution: c:/users/username/folderAtRoot/folder1/folder2/folder3

Root: c:/users/username/folderAtRoot/folder1/folder2/folder3

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              |                                                                                                |           |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               |                                                                                                |           |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                |                                                                                                |           |
| c:/users/username/dir/somefile.d.ts                                                            |                                                                                                |           |
| c:/users/username/dir/subdir/somefile.d.ts                                                     |                                                                                                |           |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           | c:/users/username/folderAtRoot/folder1                                                         | false     |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       | c:/users/username/folderAtRoot/folder1/dir                                                     | true      |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                | c:/users/username/folderAtRoot/folder1/dir                                                     | true      |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   | c:/users/username/folderAtRoot/folder1/folder2                                                 | false     |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               | c:/users/username/folderAtRoot/folder1/folder2/dir                                             | true      |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        | c:/users/username/folderAtRoot/folder1/folder2/dir                                             | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           | c:/users/username/folderAtRoot/folder1/folder2/folder3                                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       | c:/users/username/folderAtRoot/folder1/folder2/folder3/dir                                     | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                | c:/users/username/folderAtRoot/folder1/folder2/folder3/dir                                     | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4                                 | true      |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      |                                                                                                |           |
| c:/user/dir/subdir/somefile.d.ts                                                               |                                                                                                |           |
| c:/user/username/somefile.d.ts                                                                 |                                                                                                |           |
| c:/user/username/dir/somefile.d.ts                                                             |                                                                                                |           |
| c:/user/username/dir/subdir/somefile.d.ts                                                      |                                                                                                |           |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |

## RootDirForResolution: c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4

Root: c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              |                                                                                                |           |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               |                                                                                                |           |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                |                                                                                                |           |
| c:/users/username/dir/somefile.d.ts                                                            |                                                                                                |           |
| c:/users/username/dir/subdir/somefile.d.ts                                                     |                                                                                                |           |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           | c:/users/username/folderAtRoot/folder1                                                         | false     |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       | c:/users/username/folderAtRoot/folder1/dir                                                     | true      |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                | c:/users/username/folderAtRoot/folder1/dir                                                     | true      |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   | c:/users/username/folderAtRoot/folder1/folder2                                                 | false     |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               | c:/users/username/folderAtRoot/folder1/folder2/dir                                             | true      |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        | c:/users/username/folderAtRoot/folder1/folder2/dir                                             | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           | c:/users/username/folderAtRoot/folder1/folder2/folder3                                         | false     |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       | c:/users/username/folderAtRoot/folder1/folder2/folder3/dir                                     | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                | c:/users/username/folderAtRoot/folder1/folder2/folder3/dir                                     | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4                                 | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir                             | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir                             | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5                         | true      |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      |                                                                                                |           |
| c:/user/dir/subdir/somefile.d.ts                                                               |                                                                                                |           |
| c:/user/username/somefile.d.ts                                                                 |                                                                                                |           |
| c:/user/username/dir/somefile.d.ts                                                             |                                                                                                |           |
| c:/user/username/dir/subdir/somefile.d.ts                                                      |                                                                                                |           |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |

## RootDirForResolution: c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5

Root: c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              |                                                                                                |           |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               |                                                                                                |           |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                |                                                                                                |           |
| c:/users/username/dir/somefile.d.ts                                                            |                                                                                                |           |
| c:/users/username/dir/subdir/somefile.d.ts                                                     |                                                                                                |           |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           | c:/users/username/folderAtRoot/folder1                                                         | false     |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       | c:/users/username/folderAtRoot/folder1/dir                                                     | true      |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                | c:/users/username/folderAtRoot/folder1/dir                                                     | true      |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   | c:/users/username/folderAtRoot/folder1/folder2                                                 | false     |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               | c:/users/username/folderAtRoot/folder1/folder2/dir                                             | true      |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        | c:/users/username/folderAtRoot/folder1/folder2/dir                                             | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           | c:/users/username/folderAtRoot/folder1/folder2/folder3                                         | false     |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       | c:/users/username/folderAtRoot/folder1/folder2/folder3/dir                                     | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                | c:/users/username/folderAtRoot/folder1/folder2/folder3/dir                                     | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4                                 | false     |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir                             | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir                             | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5                         | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir                     | true      |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir                     | true      |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      |                                                                                                |           |
| c:/user/dir/subdir/somefile.d.ts                                                               |                                                                                                |           |
| c:/user/username/somefile.d.ts                                                                 |                                                                                                |           |
| c:/user/username/dir/somefile.d.ts                                                             |                                                                                                |           |
| c:/user/username/dir/subdir/somefile.d.ts                                                      |                                                                                                |           |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                |                                                                                                |           |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        |                                                                                                |           |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |

## RootDirForResolution: c:/user

Root: c:/user

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              |                                                                                                |           |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               |                                                                                                |           |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                |                                                                                                |           |
| c:/users/username/dir/somefile.d.ts                                                            |                                                                                                |           |
| c:/users/username/dir/subdir/somefile.d.ts                                                     |                                                                                                |           |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |
| c:/user/somefile.d.ts                                                                          | c:/user                                                                                        | true      |
| c:/user/dir/somefile.d.ts                                                                      | c:/user/dir                                                                                    | true      |
| c:/user/dir/subdir/somefile.d.ts                                                               | c:/user/dir                                                                                    | true      |
| c:/user/username/somefile.d.ts                                                                 | c:/user/username                                                                               | true      |
| c:/user/username/dir/somefile.d.ts                                                             | c:/user/username                                                                               | true      |
| c:/user/username/dir/subdir/somefile.d.ts                                                      | c:/user/username                                                                               | true      |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    | c:/user/username                                                                               | true      |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                | c:/user/username                                                                               | true      |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         | c:/user/username                                                                               | true      |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            | c:/user/username                                                                               | true      |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        | c:/user/username                                                                               | true      |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 | c:/user/username                                                                               | true      |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    | c:/user/username                                                                               | true      |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                | c:/user/username                                                                               | true      |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         | c:/user/username                                                                               | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            | c:/user/username                                                                               | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        | c:/user/username                                                                               | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 | c:/user/username                                                                               | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    | c:/user/username                                                                               | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                | c:/user/username                                                                               | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         | c:/user/username                                                                               | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            | c:/user/username                                                                               | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        | c:/user/username                                                                               | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts | c:/user/username                                                                               | true      |

## RootDirForResolution: c:/user/username

Root: c:/user/username

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              |                                                                                                |           |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               |                                                                                                |           |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                |                                                                                                |           |
| c:/users/username/dir/somefile.d.ts                                                            |                                                                                                |           |
| c:/users/username/dir/subdir/somefile.d.ts                                                     |                                                                                                |           |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      |                                                                                                |           |
| c:/user/dir/subdir/somefile.d.ts                                                               |                                                                                                |           |
| c:/user/username/somefile.d.ts                                                                 | c:/user/username                                                                               | true      |
| c:/user/username/dir/somefile.d.ts                                                             | c:/user/username/dir                                                                           | true      |
| c:/user/username/dir/subdir/somefile.d.ts                                                      | c:/user/username/dir                                                                           | true      |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    | c:/user/username/folderAtRoot                                                                  | true      |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                | c:/user/username/folderAtRoot                                                                  | true      |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         | c:/user/username/folderAtRoot                                                                  | true      |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            | c:/user/username/folderAtRoot                                                                  | true      |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        | c:/user/username/folderAtRoot                                                                  | true      |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 | c:/user/username/folderAtRoot                                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    | c:/user/username/folderAtRoot                                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                | c:/user/username/folderAtRoot                                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         | c:/user/username/folderAtRoot                                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            | c:/user/username/folderAtRoot                                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        | c:/user/username/folderAtRoot                                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 | c:/user/username/folderAtRoot                                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    | c:/user/username/folderAtRoot                                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                | c:/user/username/folderAtRoot                                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         | c:/user/username/folderAtRoot                                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            | c:/user/username/folderAtRoot                                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        | c:/user/username/folderAtRoot                                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts | c:/user/username/folderAtRoot                                                                  | true      |

## RootDirForResolution: c:/user/username/folderAtRoot

Root: c:/user/username/folderAtRoot

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              |                                                                                                |           |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               |                                                                                                |           |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                |                                                                                                |           |
| c:/users/username/dir/somefile.d.ts                                                            |                                                                                                |           |
| c:/users/username/dir/subdir/somefile.d.ts                                                     |                                                                                                |           |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      |                                                                                                |           |
| c:/user/dir/subdir/somefile.d.ts                                                               |                                                                                                |           |
| c:/user/username/somefile.d.ts                                                                 | c:/user/username                                                                               | false     |
| c:/user/username/dir/somefile.d.ts                                                             | c:/user/username/dir                                                                           | true      |
| c:/user/username/dir/subdir/somefile.d.ts                                                      | c:/user/username/dir                                                                           | true      |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    | c:/user/username/folderAtRoot                                                                  | true      |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                | c:/user/username/folderAtRoot/dir                                                              | true      |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         | c:/user/username/folderAtRoot/dir                                                              | true      |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            | c:/user/username/folderAtRoot/folder1                                                          | true      |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        | c:/user/username/folderAtRoot/folder1                                                          | true      |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 | c:/user/username/folderAtRoot/folder1                                                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    | c:/user/username/folderAtRoot/folder1                                                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                | c:/user/username/folderAtRoot/folder1                                                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         | c:/user/username/folderAtRoot/folder1                                                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            | c:/user/username/folderAtRoot/folder1                                                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        | c:/user/username/folderAtRoot/folder1                                                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 | c:/user/username/folderAtRoot/folder1                                                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    | c:/user/username/folderAtRoot/folder1                                                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                | c:/user/username/folderAtRoot/folder1                                                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         | c:/user/username/folderAtRoot/folder1                                                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            | c:/user/username/folderAtRoot/folder1                                                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        | c:/user/username/folderAtRoot/folder1                                                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts | c:/user/username/folderAtRoot/folder1                                                          | true      |

## RootDirForResolution: c:/user/username/folderAtRoot/folder1

Root: c:/user/username/folderAtRoot/folder1

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              |                                                                                                |           |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               |                                                                                                |           |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                |                                                                                                |           |
| c:/users/username/dir/somefile.d.ts                                                            |                                                                                                |           |
| c:/users/username/dir/subdir/somefile.d.ts                                                     |                                                                                                |           |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      |                                                                                                |           |
| c:/user/dir/subdir/somefile.d.ts                                                               |                                                                                                |           |
| c:/user/username/somefile.d.ts                                                                 | c:/user/username                                                                               | false     |
| c:/user/username/dir/somefile.d.ts                                                             | c:/user/username/dir                                                                           | true      |
| c:/user/username/dir/subdir/somefile.d.ts                                                      | c:/user/username/dir                                                                           | true      |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    | c:/user/username/folderAtRoot                                                                  | false     |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                | c:/user/username/folderAtRoot/dir                                                              | true      |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         | c:/user/username/folderAtRoot/dir                                                              | true      |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            | c:/user/username/folderAtRoot/folder1                                                          | true      |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        | c:/user/username/folderAtRoot/folder1/dir                                                      | true      |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 | c:/user/username/folderAtRoot/folder1/dir                                                      | true      |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    | c:/user/username/folderAtRoot/folder1/folder2                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                | c:/user/username/folderAtRoot/folder1/folder2                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         | c:/user/username/folderAtRoot/folder1/folder2                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            | c:/user/username/folderAtRoot/folder1/folder2                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        | c:/user/username/folderAtRoot/folder1/folder2                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 | c:/user/username/folderAtRoot/folder1/folder2                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    | c:/user/username/folderAtRoot/folder1/folder2                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                | c:/user/username/folderAtRoot/folder1/folder2                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         | c:/user/username/folderAtRoot/folder1/folder2                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            | c:/user/username/folderAtRoot/folder1/folder2                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        | c:/user/username/folderAtRoot/folder1/folder2                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts | c:/user/username/folderAtRoot/folder1/folder2                                                  | true      |

## RootDirForResolution: c:/user/username/folderAtRoot/folder1/folder2

Root: c:/user/username/folderAtRoot/folder1/folder2

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              |                                                                                                |           |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               |                                                                                                |           |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                |                                                                                                |           |
| c:/users/username/dir/somefile.d.ts                                                            |                                                                                                |           |
| c:/users/username/dir/subdir/somefile.d.ts                                                     |                                                                                                |           |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      |                                                                                                |           |
| c:/user/dir/subdir/somefile.d.ts                                                               |                                                                                                |           |
| c:/user/username/somefile.d.ts                                                                 | c:/user/username                                                                               | false     |
| c:/user/username/dir/somefile.d.ts                                                             | c:/user/username/dir                                                                           | true      |
| c:/user/username/dir/subdir/somefile.d.ts                                                      | c:/user/username/dir                                                                           | true      |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    | c:/user/username/folderAtRoot                                                                  | false     |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                | c:/user/username/folderAtRoot/dir                                                              | true      |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         | c:/user/username/folderAtRoot/dir                                                              | true      |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            | c:/user/username/folderAtRoot/folder1                                                          | false     |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        | c:/user/username/folderAtRoot/folder1/dir                                                      | true      |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 | c:/user/username/folderAtRoot/folder1/dir                                                      | true      |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    | c:/user/username/folderAtRoot/folder1/folder2                                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                | c:/user/username/folderAtRoot/folder1/folder2/dir                                              | true      |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         | c:/user/username/folderAtRoot/folder1/folder2/dir                                              | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            | c:/user/username/folderAtRoot/folder1/folder2/folder3                                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        | c:/user/username/folderAtRoot/folder1/folder2/folder3                                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 | c:/user/username/folderAtRoot/folder1/folder2/folder3                                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    | c:/user/username/folderAtRoot/folder1/folder2/folder3                                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                | c:/user/username/folderAtRoot/folder1/folder2/folder3                                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         | c:/user/username/folderAtRoot/folder1/folder2/folder3                                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            | c:/user/username/folderAtRoot/folder1/folder2/folder3                                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        | c:/user/username/folderAtRoot/folder1/folder2/folder3                                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts | c:/user/username/folderAtRoot/folder1/folder2/folder3                                          | true      |

## RootDirForResolution: c:/user/username/folderAtRoot/folder1/folder2/folder3

Root: c:/user/username/folderAtRoot/folder1/folder2/folder3

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              |                                                                                                |           |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               |                                                                                                |           |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                |                                                                                                |           |
| c:/users/username/dir/somefile.d.ts                                                            |                                                                                                |           |
| c:/users/username/dir/subdir/somefile.d.ts                                                     |                                                                                                |           |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      |                                                                                                |           |
| c:/user/dir/subdir/somefile.d.ts                                                               |                                                                                                |           |
| c:/user/username/somefile.d.ts                                                                 | c:/user/username                                                                               | false     |
| c:/user/username/dir/somefile.d.ts                                                             | c:/user/username/dir                                                                           | true      |
| c:/user/username/dir/subdir/somefile.d.ts                                                      | c:/user/username/dir                                                                           | true      |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    | c:/user/username/folderAtRoot                                                                  | false     |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                | c:/user/username/folderAtRoot/dir                                                              | true      |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         | c:/user/username/folderAtRoot/dir                                                              | true      |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            | c:/user/username/folderAtRoot/folder1                                                          | false     |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        | c:/user/username/folderAtRoot/folder1/dir                                                      | true      |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 | c:/user/username/folderAtRoot/folder1/dir                                                      | true      |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    | c:/user/username/folderAtRoot/folder1/folder2                                                  | false     |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                | c:/user/username/folderAtRoot/folder1/folder2/dir                                              | true      |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         | c:/user/username/folderAtRoot/folder1/folder2/dir                                              | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            | c:/user/username/folderAtRoot/folder1/folder2/folder3                                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        | c:/user/username/folderAtRoot/folder1/folder2/folder3/dir                                      | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 | c:/user/username/folderAtRoot/folder1/folder2/folder3/dir                                      | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4                                  | true      |

## RootDirForResolution: c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4

Root: c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              |                                                                                                |           |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               |                                                                                                |           |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                |                                                                                                |           |
| c:/users/username/dir/somefile.d.ts                                                            |                                                                                                |           |
| c:/users/username/dir/subdir/somefile.d.ts                                                     |                                                                                                |           |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      |                                                                                                |           |
| c:/user/dir/subdir/somefile.d.ts                                                               |                                                                                                |           |
| c:/user/username/somefile.d.ts                                                                 | c:/user/username                                                                               | false     |
| c:/user/username/dir/somefile.d.ts                                                             | c:/user/username/dir                                                                           | true      |
| c:/user/username/dir/subdir/somefile.d.ts                                                      | c:/user/username/dir                                                                           | true      |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    | c:/user/username/folderAtRoot                                                                  | false     |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                | c:/user/username/folderAtRoot/dir                                                              | true      |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         | c:/user/username/folderAtRoot/dir                                                              | true      |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            | c:/user/username/folderAtRoot/folder1                                                          | false     |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        | c:/user/username/folderAtRoot/folder1/dir                                                      | true      |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 | c:/user/username/folderAtRoot/folder1/dir                                                      | true      |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    | c:/user/username/folderAtRoot/folder1/folder2                                                  | false     |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                | c:/user/username/folderAtRoot/folder1/folder2/dir                                              | true      |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         | c:/user/username/folderAtRoot/folder1/folder2/dir                                              | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            | c:/user/username/folderAtRoot/folder1/folder2/folder3                                          | false     |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        | c:/user/username/folderAtRoot/folder1/folder2/folder3/dir                                      | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 | c:/user/username/folderAtRoot/folder1/folder2/folder3/dir                                      | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4                                  | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir                              | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir                              | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5                          | true      |

## RootDirForResolution: c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5

Root: c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    |                                                                                                |           |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              |                                                                                                |           |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      |                                                                                                |           |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               |                                                                                                |           |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                |                                                                                                |           |
| c:/users/username/dir/somefile.d.ts                                                            |                                                                                                |           |
| c:/users/username/dir/subdir/somefile.d.ts                                                     |                                                                                                |           |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       |                                                                                                |           |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts |                                                                                                |           |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      |                                                                                                |           |
| c:/user/dir/subdir/somefile.d.ts                                                               |                                                                                                |           |
| c:/user/username/somefile.d.ts                                                                 | c:/user/username                                                                               | false     |
| c:/user/username/dir/somefile.d.ts                                                             | c:/user/username/dir                                                                           | true      |
| c:/user/username/dir/subdir/somefile.d.ts                                                      | c:/user/username/dir                                                                           | true      |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    | c:/user/username/folderAtRoot                                                                  | false     |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                | c:/user/username/folderAtRoot/dir                                                              | true      |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         | c:/user/username/folderAtRoot/dir                                                              | true      |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            | c:/user/username/folderAtRoot/folder1                                                          | false     |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        | c:/user/username/folderAtRoot/folder1/dir                                                      | true      |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 | c:/user/username/folderAtRoot/folder1/dir                                                      | true      |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    | c:/user/username/folderAtRoot/folder1/folder2                                                  | false     |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                | c:/user/username/folderAtRoot/folder1/folder2/dir                                              | true      |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         | c:/user/username/folderAtRoot/folder1/folder2/dir                                              | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            | c:/user/username/folderAtRoot/folder1/folder2/folder3                                          | false     |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        | c:/user/username/folderAtRoot/folder1/folder2/folder3/dir                                      | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 | c:/user/username/folderAtRoot/folder1/folder2/folder3/dir                                      | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4                                  | false     |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir                              | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir                              | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5                          | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir                      | true      |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir                      | true      |

## RootDirForResolution: undefined

Root: undefined

| Location                                                                                       | getDirectoryToWatchFailedLookupLocation                                                        | Recursive |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------- |
| c:/somefile.d.ts                                                                               |                                                                                                |           |
| c:/dir/somefile.d.ts                                                                           |                                                                                                |           |
| c:/dir/subdir/somefile.d.ts                                                                    | c:/dir/subdir                                                                                  | false     |
| c:/folderAtRoot/somefile.d.ts                                                                  |                                                                                                |           |
| c:/folderAtRoot/dir/somefile.d.ts                                                              | c:/folderAtRoot/dir                                                                            | false     |
| c:/folderAtRoot/dir/subdir/somefile.d.ts                                                       | c:/folderAtRoot/dir/subdir                                                                     | false     |
| c:/folderAtRoot/folder1/somefile.d.ts                                                          | c:/folderAtRoot/folder1                                                                        | false     |
| c:/folderAtRoot/folder1/dir/somefile.d.ts                                                      | c:/folderAtRoot/folder1/dir                                                                    | false     |
| c:/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                               | c:/folderAtRoot/folder1/dir/subdir                                                             | false     |
| c:/folderAtRoot/folder1/folder2/somefile.d.ts                                                  | c:/folderAtRoot/folder1/folder2                                                                | false     |
| c:/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                              | c:/folderAtRoot/folder1/folder2/dir                                                            | false     |
| c:/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                                       | c:/folderAtRoot/folder1/folder2/dir/subdir                                                     | false     |
| c:/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                                          | c:/folderAtRoot/folder1/folder2/folder3                                                        | false     |
| c:/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                                      | c:/folderAtRoot/folder1/folder2/folder3/dir                                                    | false     |
| c:/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                               | c:/folderAtRoot/folder1/folder2/folder3/dir/subdir                                             | false     |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                                  | c:/folderAtRoot/folder1/folder2/folder3/folder4                                                | false     |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                              | c:/folderAtRoot/folder1/folder2/folder3/folder4/dir                                            | false     |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts                       | c:/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir                                     | false     |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts                          | c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5                                        | false     |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts                      | c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir                                    | false     |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts               | c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir                             | false     |
| c:/users/somefile.d.ts                                                                         |                                                                                                |           |
| c:/users/dir/somefile.d.ts                                                                     |                                                                                                |           |
| c:/users/dir/subdir/somefile.d.ts                                                              |                                                                                                |           |
| c:/users/username/somefile.d.ts                                                                |                                                                                                |           |
| c:/users/username/dir/somefile.d.ts                                                            |                                                                                                |           |
| c:/users/username/dir/subdir/somefile.d.ts                                                     | c:/users/username/dir/subdir                                                                   | false     |
| c:/users/username/folderAtRoot/somefile.d.ts                                                   |                                                                                                |           |
| c:/users/username/folderAtRoot/dir/somefile.d.ts                                               | c:/users/username/folderAtRoot/dir                                                             | false     |
| c:/users/username/folderAtRoot/dir/subdir/somefile.d.ts                                        | c:/users/username/folderAtRoot/dir/subdir                                                      | false     |
| c:/users/username/folderAtRoot/folder1/somefile.d.ts                                           | c:/users/username/folderAtRoot/folder1                                                         | false     |
| c:/users/username/folderAtRoot/folder1/dir/somefile.d.ts                                       | c:/users/username/folderAtRoot/folder1/dir                                                     | false     |
| c:/users/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                | c:/users/username/folderAtRoot/folder1/dir/subdir                                              | false     |
| c:/users/username/folderAtRoot/folder1/folder2/somefile.d.ts                                   | c:/users/username/folderAtRoot/folder1/folder2                                                 | false     |
| c:/users/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                               | c:/users/username/folderAtRoot/folder1/folder2/dir                                             | false     |
| c:/users/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                        | c:/users/username/folderAtRoot/folder1/folder2/dir/subdir                                      | false     |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                           | c:/users/username/folderAtRoot/folder1/folder2/folder3                                         | false     |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                       | c:/users/username/folderAtRoot/folder1/folder2/folder3/dir                                     | false     |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                | c:/users/username/folderAtRoot/folder1/folder2/folder3/dir/subdir                              | false     |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                   | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4                                 | false     |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts               | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir                             | false     |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts        | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir                      | false     |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts           | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5                         | false     |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts       | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir                     | false     |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts | c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir              | false     |
| c:/user/somefile.d.ts                                                                          |                                                                                                |           |
| c:/user/dir/somefile.d.ts                                                                      | c:/user/dir                                                                                    | false     |
| c:/user/dir/subdir/somefile.d.ts                                                               | c:/user/dir/subdir                                                                             | false     |
| c:/user/username/somefile.d.ts                                                                 | c:/user/username                                                                               | false     |
| c:/user/username/dir/somefile.d.ts                                                             | c:/user/username/dir                                                                           | false     |
| c:/user/username/dir/subdir/somefile.d.ts                                                      | c:/user/username/dir/subdir                                                                    | false     |
| c:/user/username/folderAtRoot/somefile.d.ts                                                    | c:/user/username/folderAtRoot                                                                  | false     |
| c:/user/username/folderAtRoot/dir/somefile.d.ts                                                | c:/user/username/folderAtRoot/dir                                                              | false     |
| c:/user/username/folderAtRoot/dir/subdir/somefile.d.ts                                         | c:/user/username/folderAtRoot/dir/subdir                                                       | false     |
| c:/user/username/folderAtRoot/folder1/somefile.d.ts                                            | c:/user/username/folderAtRoot/folder1                                                          | false     |
| c:/user/username/folderAtRoot/folder1/dir/somefile.d.ts                                        | c:/user/username/folderAtRoot/folder1/dir                                                      | false     |
| c:/user/username/folderAtRoot/folder1/dir/subdir/somefile.d.ts                                 | c:/user/username/folderAtRoot/folder1/dir/subdir                                               | false     |
| c:/user/username/folderAtRoot/folder1/folder2/somefile.d.ts                                    | c:/user/username/folderAtRoot/folder1/folder2                                                  | false     |
| c:/user/username/folderAtRoot/folder1/folder2/dir/somefile.d.ts                                | c:/user/username/folderAtRoot/folder1/folder2/dir                                              | false     |
| c:/user/username/folderAtRoot/folder1/folder2/dir/subdir/somefile.d.ts                         | c:/user/username/folderAtRoot/folder1/folder2/dir/subdir                                       | false     |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/somefile.d.ts                            | c:/user/username/folderAtRoot/folder1/folder2/folder3                                          | false     |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/somefile.d.ts                        | c:/user/username/folderAtRoot/folder1/folder2/folder3/dir                                      | false     |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir/somefile.d.ts                 | c:/user/username/folderAtRoot/folder1/folder2/folder3/dir/subdir                               | false     |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/somefile.d.ts                    | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4                                  | false     |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/somefile.d.ts                | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir                              | false     |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir/somefile.d.ts         | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/dir/subdir                       | false     |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/somefile.d.ts            | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5                          | false     |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/somefile.d.ts        | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir                      | false     |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir/somefile.d.ts | c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/dir/subdir               | false     |

