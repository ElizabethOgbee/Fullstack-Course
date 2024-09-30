## Exercises 0.4.-0.6.
### New Note Input Diagram

### 0.4
sequenceDiagram
participant user
participant browser
participant server

user->>browser: writes a new note in the text field
user->>browser: saves text by clicking the save button

Notes right of browser: The browser captures the saved input 

browser->>server: Post https://studies.cs.helsinki.fi/exampleapp/notes to update the server

Notes right of server: server recieves the new note and start processing it

server->>browser: responds and send the respond(either a confirmation or an error)

Note right of browser: browser recieves server's response

browser->>user: update the page with the new note

### 0.5
sequenceDiagram
participant browser
participant server

browser->>server: Get https://studies.cs.helsinki.fi/exampleapp/notes
activate server
server->>browser: HTML document
deactivate server

browser->>server: Get https://studies.cs.helsinki.fi/exampleapp/main.css
activate server
server->>browser: CSS file
deactivate server

browser->>server: Get https://studies.cs.helsinki.fi/exampleapp/main.css
activate server
server->>browser: the Javascript file
deactivate server

Note right of browser: browser starts executing processing the js file to access the Json content

browser->>: Get https://studies.cs.helsinki.fi/exampleapp/data.json
activate server
server->>browser: Get [{"content": "Saludos desde mexico tambien
", "date": "9/24/2024"}, ...]
deactivate server

Notes of brower: The browser executes the callback function that renderes the notes

### 0.6

sequenceDiagram
participant: User
participant: browser
participant: server

user->>browser: writes a new note in the text field
user->>browser: saves text by clicking the save button

Notes right of browser: The browser captures the saved input 

browser->>server: Post https://studies.cs.helsinki.fi/exampleapp/new_note to update the server

Notes right of server: server recieves the new note and start processing it

server->>browser: responds and send the respond(either a confirmation or an error)

Note right of browser: browser recieves server's response

browser->>user: update the page with the new note