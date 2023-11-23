sequenceDiagram
    participant browser
    participant server
    participant user

    Note right of browser: User interacts with the web page

    user->browser: Open https://studies.cs.helsinki.fi/exampleapp/notes
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    user->browser: Write note in text field
    user->browser: Click on Save button

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    server-->>browser: New note data
    deactivate server

    browser-->>user: Confirmation message

    Note right of browser: The browser may update the UI to reflect the new note
