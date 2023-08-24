[![](https://mermaid.ink/img/pako:eNq9VE1v2zAM_SuEzom9djcfetqwoVjbAclt3oGV6FipLXkSnbYI8t9HW06QtcCWfmA-SY8UH0mTb6u0N6QKFelXT07TJ4urgG3pSgfydRjYatuhY7gN_j5SeG4QcDPgoyWZJ1-YX1wkawHfbxZLqJm7WOR55N5YipmOWU1NtO7OZpXN6QHbriHsutwgY7aOfkrk2jNBsKuawVf78AUsazpw0QPpnikCC7jGDUYdbMfAHtCYEXV0D26IJNiBANAZCGRsID1654NLTLyo2W5QXuyLHMB0Pi7u8Pz0Ao9IDD2jSYZ9bUdMXz4vX0fyl0rmEv_Q0q_Lq29gvO5bcvyP_N6aXovWifmFGQ5_Uh5BZRv6HwmuX5HfpczfIs3fCWmeMN2RZePiNOTWrZ6yDHssGAofsa6nNbhc3FxDFXw73t63N0829NTu_NhCKarjeBgvVchlnDgrtWF8LNVMEAlNyXb-4fzj_Gx-VirYzSDLMvj59l7-oRQam-YW9R1UvZOIogdjFwM5QyG5TFukZqqlICNhRDC3A1upxNxOqRqqsG-kptLtxBV79otHp1XBoaeZ6ruhqklfVVFhEwUV3WAfrpIIj1q8-w1GC_Po?type=png)](https://mermaid.live/edit#pako:eNq9VE1v2zAM_SuEzom9djcfetqwoVjbAclt3oGV6FipLXkSnbYI8t9HW06QtcCWfmA-SY8UH0mTb6u0N6QKFelXT07TJ4urgG3pSgfydRjYatuhY7gN_j5SeG4QcDPgoyWZJ1-YX1wkawHfbxZLqJm7WOR55N5YipmOWU1NtO7OZpXN6QHbriHsutwgY7aOfkrk2jNBsKuawVf78AUsazpw0QPpnikCC7jGDUYdbMfAHtCYEXV0D26IJNiBANAZCGRsID1654NLTLyo2W5QXuyLHMB0Pi7u8Pz0Ao9IDD2jSYZ9bUdMXz4vX0fyl0rmEv_Q0q_Lq29gvO5bcvyP_N6aXovWifmFGQ5_Uh5BZRv6HwmuX5HfpczfIs3fCWmeMN2RZePiNOTWrZ6yDHssGAofsa6nNbhc3FxDFXw73t63N0829NTu_NhCKarjeBgvVchlnDgrtWF8LNVMEAlNyXb-4fzj_Gx-VirYzSDLMvj59l7-oRQam-YW9R1UvZOIogdjFwM5QyG5TFukZqqlICNhRDC3A1upxNxOqRqqsG-kptLtxBV79otHp1XBoaeZ6ruhqklfVVFhEwUV3WAfrpIIj1q8-w1GC_Po)
sequenceDiagram

    participant browser
    participant server

   
    browser ->>server: POST https://studies.cs.helsinki.fi/exampleapp/data.json
    Note right of browser: The browser executes the javascript to add the new note to data.json and redirect to /notes
    activate server
    server ->>server: redirect https://studies.cs.helsinki.fi/exampleapp/notes
    deactivate server

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
