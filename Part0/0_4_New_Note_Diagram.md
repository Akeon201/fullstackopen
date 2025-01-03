```mermaid
sequenceDiagram
    actor u as User
    participant a as Browser
    participant b as Server

    u->a: Creates new note on web page and submits it

    a->>+b: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    b-->>-a: Redirect

    a->>+b: GET https://studies.cs.helsinki.fi/exampleapp/notes
    b-->>-a: HTML document

    a->>+b: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    b-->>-a: CSS file

    a->>+b: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    b-->>-a: JavaScript file
    Note right of a: Browser executes JavaScript, fetching JSON from server

    a->>+b: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    b-->>-a: [{"content":"piippola","date":"2025-01-01T13:35:24.466Z"}, ...]
    Note right of a: Browser executes callback function, rendering notes

    a->u: Views loaded web page
```
