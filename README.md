**Test Cases for PoetryDB API**

- **TC01: Empty query**
    - Send a GET request to the following URL: https://poetrydb.org/author//lines.json
    - Assert that the JSON response is an empty list.
    - Validation: We will use the assert statement in Python to validate the expected result. The assert statement will raise an AssertionError if the condition is not met.

- **TC02: Author query**
    - Send a GET request to the following URL: https://poetrydb.org/author/Shelley/lines.json
    - Parse the JSON response and store the titles of the poems in a list.
    - Assert that the list of titles contains at least one title.
    - Validation: We will use the assert statement in Python to validate the expected result. The assert statement will raise an AssertionError if the condition is not met.

- **TC03: Title query**
    - Send a GET request to the following URL: https://poetrydb.org/title/The%20Raven/author.json
    - Parse the JSON response and store the author of the poem in a variable.
    - Assert that the author of the poem is "Edgar Allan Poe".
    - Validation: We will use the assert statement in Python to validate the expected result. The assert statement will raise an AssertionError if the condition is not met.

- **TC04: Lines query**
    - Send a GET request to the following URL: https://poetrydb.org/lines/Life%20is%20Fine/author.json
    - Parse the JSON response and store the author of the poem in a variable.
    - Assert that the author of the poem is "Langston Hughes".
    - Validation: We will use the assert statement in Python to validate the expected result. The assert statement will raise an AssertionError if the condition is not met.

- **TC05: Linecount query**
    - Send a GET request to the following URL: https://poetrydb.org/linecount/8/author.json
    - Parse the JSON response and store the author of the poem in a variable.
    - Assert that the author of the poem is "William Blake".
    - Validation: We will use the assert statement in Python to validate the expected result. The assert statement will raise an AssertionError if the condition is not met.

- **TC06: Poemcount query**
    - Send a GET request to the following URL: https://poetrydb.org/poemcount/2/author.json
    - Parse the JSON response and store the author of the poem in a variable.
    - Assert that the author of the poem is "Emily Dickinson".
    - Validation: We will use the assert statement in Python to validate the expected result. The assert statement will raise an AssertionError if the condition is not met.

- **TC07: Random query**
    - Send a GET request to the following URL: https://poetrydb.org/random/1/author.json
    - Parse the JSON response and store the author of the poem in a variable.
    - Assert that the author of the poem is not an empty string.
    - Validation: We will use the assert statement in Python to validate the expected result. The assert statement will raise an AssertionError if the condition is not met.
