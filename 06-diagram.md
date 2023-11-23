sequenceDiagram
    participant user
    participant browser
    participant spa
    participant server
    

    Note right of browser: User interacts with the SPA

    user->browser: Open SPA at https://studies.cs.helsinki.fi/exampleapp/spa
    browser->>spa: Load SPA files
    activate spa
    spa-->>browser: SPA loaded
    deactivate spa

    user->browser: Write a new note
    user->browser: Click on Save button

    browser->>spa: Capture user input
    spa->>server: POST request to create new note
    activate server
    server-->>spa: New note created, return response
    deactivate server

    spa-->>browser: Confirmation message
    Note right of browser: SPA may update the UI to show the new note

    browser->>spa: User continues interacting with SPA
