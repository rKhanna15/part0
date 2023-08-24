[![](https://mermaid.ink/img/pako:eNq9VE1v2zAM_SuEzonTj5sPPW3oMPRjQHKbd2AlOlZrS55EpS2C_PfRlpG16yVpi_lkPVLk4yPFrdLekCpVpN-JnKYvFtcBu8qBfD0Gttr26Bjugn-MFN4aBNwMeLZMbvOLi4yXcPl1BQ1zH8vFInIylmKhY9FQG617sEVtF_SEXd8S9v3CeaaYQ6Fmu0GmfYYBzP9ziT9lKuHb6voKjNepI8fZy9Cby59Dr0PrxHwkQ24I5BLUtqX_QfD-Hfy-4waXOtieD6F5I22CYNcNg69hH2glgaYDRJYhiUBPpBNbt_43yzB4gqHkI9YNxeywvL2BOvhuPH2uNgYZRRvvjlPn5xYqeSaOh_FSpRzGibNSG8bnSs0EkdCUbWcnZ-fz0_lppWA3g6Io4NfHtcwiThJpbNs71A9QJycRvcsqBnKGQnaZXtEr2eCFbj9ulx8Q7ljC99L0mJvOHtCYzJEeR54Dtk8A6IxUYmwgPXofuBBeFre__q6t8zfeUQtGzVRHQV6fkWW6HZwqJVV201QYqjG1Mj6V24krJvbLZ6dVySHRTKV-GKBp96qyxjYKKnWwD9d5QY97evcH3gL9xg?type=png)](https://mermaid.live/edit#pako:eNq9VE1v2zAM_SuEzonTj5sPPW3oMPRjQHKbd2AlOlZrS55EpS2C_PfRlpG16yVpi_lkPVLk4yPFrdLekCpVpN-JnKYvFtcBu8qBfD0Gttr26Bjugn-MFN4aBNwMeLZMbvOLi4yXcPl1BQ1zH8vFInIylmKhY9FQG617sEVtF_SEXd8S9v3CeaaYQ6Fmu0GmfYYBzP9ziT9lKuHb6voKjNepI8fZy9Cby59Dr0PrxHwkQ24I5BLUtqX_QfD-Hfy-4waXOtieD6F5I22CYNcNg69hH2glgaYDRJYhiUBPpBNbt_43yzB4gqHkI9YNxeywvL2BOvhuPH2uNgYZRRvvjlPn5xYqeSaOh_FSpRzGibNSG8bnSs0EkdCUbWcnZ-fz0_lppWA3g6Io4NfHtcwiThJpbNs71A9QJycRvcsqBnKGQnaZXtEr2eCFbj9ulx8Q7ljC99L0mJvOHtCYzJEeR54Dtk8A6IxUYmwgPXofuBBeFre__q6t8zfeUQtGzVRHQV6fkWW6HZwqJVV201QYqjG1Mj6V24krJvbLZ6dVySHRTKV-GKBp96qyxjYKKnWwD9d5QY97evcH3gL9xg)
sequenceDiagram

    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes

    browser ->>server: POST https://studies.cs.helsinki.fi/exampleapp/data.json
    Note right of browser: The browser executes the javascript to add the new note to data.json and redirect to /notes
    activate server
    server ->>server: redirect https://studies.cs.helsinki.fi/exampleapp/notes
    server ->>browser: HTML document
    deactivate server
