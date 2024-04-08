Following is the list of the cases.

This is an example of manual test case:

Test case 1
Scenario: Retrieve a poem by its title from the Poetry Database API

Given the Poetry Database API is accessible
And a valid poem title "{title}" is provided

When a GET request is sent to https://poetrydb.org/title/{title}/.json

Then the response status code should be 200 OK
And the response body should be a JSON object
And the response body should contain the expected poem data
[
  {
    "title": "Title"
    "author": "Author"
    "lines": "lines"
    "linecount": "linecount"
  }
]




| Test Case |               Scenario              |                                               Steps                                              |       Expected Result      |                                       Validation Method                                       |
|:---------:|:-----------------------------------:|:------------------------------------------------------------------------------------------------:|:--------------------------:|:---------------------------------------------------------------------------------------------:|
| 1         | Get a poem by title                 | Send a GET request to https://poetrydb.org/title/{title}/.json                                    | JSON object with poem data | Compare response body to expected JSON object                                                 |
| 2         | Get a poem by author                | Send a GET request to https://poetrydb.org/author/{author}/.json                                  | JSON array with poem data  | Compare response body to expected JSON array                                                  |
| 3         | Get a poem by lines                 | Send a GET request to https://poetrydb.org/lines/{lines}/.json                                    | JSON object with poem data | Compare response body to expected JSON object                                                 |
| 4         | Get a poem by linecount             | Send a GET request to https://poetrydb.org/linecount/{linecount}/.json                            | JSON array with poem data  | Compare response body to expected JSON array                                                  |
| 5         | Get a poem by random                | Send a GET request to https://poetrydb.org/random.json                                           | JSON object with poem data | Check that response body is a valid JSON object and contains the fields: author, title, lines |
| 6         | Get a poem by author and title      | Send a GET request to https://poetrydb.org/author/{author}/title/{title}/.json                    | JSON object with poem data | Compare response body to expected JSON object                                                 |
| 7         | Get a poem by author and linecount  | Send a GET request to https://poetrydb.org/author/{author}/linecount/{linecount}/.json            | JSON array with poem data  | Compare response body to expected JSON array                                                  |
| 8         | Get a poem by title and linecount   | Send a GET request to https://poetrydb.org/title/{title}/linecount/{linecount}/.json              | JSON object with poem data | Compare response body to expected JSON object                                                 |
| 9         | Get a poem with multiple authors    | Send a GET request to https://poetrydb.org/author/{author1},{author2},.../{title}/.json           | JSON object with poem data | Compare response body to expected JSON object                                                 |
| 10        | Get a poem with multiple titles     | Send a GET request to https://poetrydb.org/title/{title1},{title2},.../{author}/.json             | JSON array with poem data  | Compare response body to expected JSON array                                                  |
| 11        | Get a poem with multiple lines      | Send a GET request to https://poetrydb.org/lines/{lines1},{lines2},.../{author}/.json             | JSON object with poem data | Compare response body to expected JSON object                                                 |
| 12        | Get a poem with multiple linecounts | Send a GET request to https://poetrydb.org/linecount/{linecount1},{linecount2},.../{author}/.json | JSON array with poem data  | Compare response body to expected JSON array                                                  |

Some Edge cases:
| Test Case |                     Scenario                     |                                               Steps                                              |       Expected Result      |                                       Validation Method                                       |
|:---------:|:------------------------------------------------:|:------------------------------------------------------------------------------------------------:|:--------------------------:|:---------------------------------------------------------------------------------------------:|
| 1         | Get a poem by a empty author using special chars | Send a GET request to https://poetrydb.org/author/\//.json                                        | 404 Not Found              | Check that the response status code is 404                                                    |
| 2         | Get a poem by a non-existent title using special chars    | Send a GET request to https://poetrydb.org/title/\/.json                                         | 404 Not Found              | Check that the response status code is 404                                                    |
| 3         | Get a poem with an invalid linecount             | Send a GET request to https://poetrydb.org/linecount/1f/.json                                     | 400 Bad Request            | Check that the response status code is 400                                                    |
| 4         | Get a poem by linecount                          | Send a GET request to https://poetrydb.org/linecount/{linecount}/.json                            | JSON array with poem data  | Compare response body to expected JSON array                                                  |
| 5         | Get a poem by random                             | Send a GET request to https://poetrydb.org/random/.json                                           | JSON object with poem data | Check that response body is a valid JSON object and contains the fields: author, title, lines |
| 6         | Get a poem by author and title                   | Send a GET request to https://poetrydb.org/author/{author}/title/{title}/.json                    | JSON object with poem data | Compare response body to expected JSON object                                                 |
| 7         | Get a poem by author and wrong linecount         | Send a GET request to https://poetrydb.org/author/{author}/3AD/{linecount}.json            | 400 Bad Request  | Compare response body to expected JSON array                                                  |
| 8         | Get a poem by title and wrong linecount          | Send a GET request to https://poetrydb.org/title/{title}/F32/{linecount}.json              | 400 Bad Request | Compare response body to expected JSON object                                                 |
| 9         | Get a poem with multiple authors                 | Send a GET request to https://poetrydb.org/author/{author1},{author2},.../{title}.json           | JSON object with poem data | Compare response body to expected JSON object                                                 |
| 10        | Get a poem with multiple titles                  | Send a GET request to https://poetrydb.org/title/{title1},{title2},.../{author}.json             | JSON array with poem data  | Compare response body to expected JSON array                                                  |
| 11        | Get a poem with multiple lines                   | Send a GET request to https://poetrydb.org/lines/{lines1},{lines2},.../{author}.json             | JSON object with poem data | Compare response body to expected JSON object                                                 |
| 12        | Get a poem with multiple linecounts              | Send a GET request to https://poetrydb.org/linecount/{linecount1},{linecount2},.../{author}.json | JSON array with poem data  | Compare response body to expected JSON array                                                  |

Negative test scenarios:
| Test Case |                Scenario                |                                               Steps                                              |       Expected Result      |                                       Validation Method                                       |
|:---------:|:--------------------------------------:|:------------------------------------------------------------------------------------------------:|:--------------------------:|:---------------------------------------------------------------------------------------------:|
| 1         | Get a poem with an empty title         | Send a GET request to https://poetrydb.org//.json                                                | 400 Bad Request            | Check that the response status code is 400                                                    |
| 2         | Get a poem with an empty author        | Send a GET request to https://poetrydb.org//.json                                                | 400 Bad Request            | Check that the response status code is 400                                                    |
| 3         | Get a poem with an empty linecount     | Send a GET request to https://poetrydb.org//.json                                                | 400 Bad Request            | Check that the response status code is 400                                                    |
| 4         | Get a poem with an invalid JSON format | Send a GET request to https://poetrydb.org/title/.txt                                            | 400 Bad Request            | Check that the response status code is 400                                                    |

