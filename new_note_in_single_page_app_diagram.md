[![](https://mermaid.ink/img/pako:eNplUbtuwzAM_BVCc5ruHjJ17QNNRgMBI9G1WptyJcpuEeTfS1s2ULSaxDve8UBejQ2OTGUSfWZiSw8e3yL2NdcM-gaM4q0fkAUuMUyJ4n9CwXHD16a7w6GgFZxa2lCgL7JZKIEoSCOpuEV2nVI9SRscTC3xwl6ySGDwCWzn7Qe5fRlQbNV_M63glSKxU49Zx0EIOp-ktD8tJTUCoYHfkdZ5SZUlDtNUxBKWujSDxoOEo2b2MlMOBffvKfDfPJv5y_PxBPfqdp7dzmnAdZlmZ3qKPXqn-77OUG10UE-1qfTrqMHcSW1qvmkrZgnHb7amkphpZ_Kgk7fzmKrBLilKzkuIj-WGyylvP_dmoyY?type=png)](https://mermaid.live/edit#pako:eNplUbtuwzAM_BVCc5ruHjJ17QNNRgMBI9G1WptyJcpuEeTfS1s2ULSaxDve8UBejQ2OTGUSfWZiSw8e3yL2NdcM-gaM4q0fkAUuMUyJ4n9CwXHD16a7w6GgFZxa2lCgL7JZKIEoSCOpuEV2nVI9SRscTC3xwl6ySGDwCWzn7Qe5fRlQbNV_M63glSKxU49Zx0EIOp-ktD8tJTUCoYHfkdZ5SZUlDtNUxBKWujSDxoOEo2b2MlMOBffvKfDfPJv5y_PxBPfqdp7dzmnAdZlmZ3qKPXqn-77OUG10UE-1qfTrqMHcSW1qvmkrZgnHb7amkphpZ_Kgk7fzmKrBLilKzkuIj-WGyylvP_dmoyY)
sequenceDiagram

    participant browser
    participant server
    browser->>server: The browser executes the event handler method when the button is clicked.
    server->> browser: Rerender the note list
    Note left of server: The method sends the new note to the server and saves it to data.json.
    server->>server: POST /new_note_spa

   
