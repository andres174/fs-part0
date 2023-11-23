sequenceDiagram
    participant browser
    participant server
    participant spa

    Note right of browser: User interacts with the SPA

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: SPA HTML, CSS, and JS files
    deactivate server

    browser->>spa: Load SPA files
    activate spa
    spa-->>browser: SPA loaded
    deactivate spa

    Note right of browser: SPA handles navigation and content dynamically

    browser->>spa: User interacts with SPA
    browser->>server: SPA makes API requests to the server
    activate server
    server-->>spa: Response to API request
    deactivate server

    Note right of browser: SPA updates the UI dynamically

    browser->>spa: User interacts further with SPA
    browser->>server: SPA makes additional API requests as needed
    activate server
    server-->>spa: Response to API request
    deactivate server

    Note right of browser: SPA continues to handle user interactions and server communication
