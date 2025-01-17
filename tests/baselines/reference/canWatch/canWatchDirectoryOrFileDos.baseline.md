# canWatchDirectoryOrFile

Determines if given directory or file can be watched

## Testing for Dos root: c:/

| Directory                                                                           | canWatchDirectoryOrFile |
| ----------------------------------------------------------------------------------- | ----------------------- |
| c:/                                                                                 | false                   |
| c:/folderAtRoot                                                                     | false                   |
| c:/folderAtRoot/folder1                                                             | true                    |
| c:/folderAtRoot/folder1/folder2                                                     | true                    |
| c:/folderAtRoot/folder1/folder2/folder3                                             | true                    |
| c:/folderAtRoot/folder1/folder2/folder3/folder4                                     | true                    |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5                             | true                    |
| c:/users                                                                            | false                   |
| c:/users/username                                                                   | false                   |
| c:/users/username/folderAtRoot                                                      | false                   |
| c:/users/username/folderAtRoot/folder1                                              | true                    |
| c:/users/username/folderAtRoot/folder1/folder2                                      | true                    |
| c:/users/username/folderAtRoot/folder1/folder2/folder3                              | true                    |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4                      | true                    |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5              | true                    |
| c:/user                                                                             | false                   |
| c:/user/username                                                                    | true                    |
| c:/user/username/folderAtRoot                                                       | true                    |
| c:/user/username/folderAtRoot/folder1                                               | true                    |
| c:/user/username/folderAtRoot/folder1/folder2                                       | true                    |
| c:/user/username/folderAtRoot/folder1/folder2/folder3                               | true                    |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4                       | true                    |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5               | true                    |

| File                                                                                | canWatchDirectoryOrFile |
| ----------------------------------------------------------------------------------- | ----------------------- |
| c:/package.json                                                                     | false                   |
| c:/folderAtRoot/package.json                                                        | true                    |
| c:/folderAtRoot/folder1/package.json                                                | true                    |
| c:/folderAtRoot/folder1/folder2/package.json                                        | true                    |
| c:/folderAtRoot/folder1/folder2/folder3/package.json                                | true                    |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/package.json                        | true                    |
| c:/folderAtRoot/folder1/folder2/folder3/folder4/folder5/package.json                | true                    |
| c:/users/package.json                                                               | false                   |
| c:/users/username/package.json                                                      | false                   |
| c:/users/username/folderAtRoot/package.json                                         | true                    |
| c:/users/username/folderAtRoot/folder1/package.json                                 | true                    |
| c:/users/username/folderAtRoot/folder1/folder2/package.json                         | true                    |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/package.json                 | true                    |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/package.json         | true                    |
| c:/users/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/package.json | true                    |
| c:/user/package.json                                                                | true                    |
| c:/user/username/package.json                                                       | true                    |
| c:/user/username/folderAtRoot/package.json                                          | true                    |
| c:/user/username/folderAtRoot/folder1/package.json                                  | true                    |
| c:/user/username/folderAtRoot/folder1/folder2/package.json                          | true                    |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/package.json                  | true                    |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/package.json          | true                    |
| c:/user/username/folderAtRoot/folder1/folder2/folder3/folder4/folder5/package.json  | true                    |

