```mermaid
sequenceDiagram  
    participant browser
    participant server

    browser->>server: GET [https://studies.cs.helsinki.fi/exampleapp/spa](https://studies.cs.helsinki.fi/exampleapp/spa)
    activate server
    server-->>browser: servidor devolve html
    deactivate server

    browser->>server: GET [https://studies.cs.helsinki.fi/exampleapp/main.css](https://studies.cs.helsinki.fi/exampleapp/main.css)
    activate server
    server-->>browser: servidor devolve o css
    deactivate server

    browser->>server: GET [https://studies.cs.helsinki.fi/exampleapp/spa.js](https://studies.cs.helsinki.fi/exampleapp/spa.js)
    activate server
    server-->>browser: servidor devolve o js
    deactivate server

    Note right of browser: O navegador começa a executar o código JavaScript que busca o JSON do servidor

    browser->>server: GET [https://studies.cs.helsinki.fi/exampleapp/data.json](https://studies.cs.helsinki.fi/exampleapp/data.json)
    activate server
    server-->>browser: servidor devolveu um listas vazia []
    deactivate server

    Note right of browser: O navegador executa a função callback (função de retorno de chamada) que renderiza as notas

    Note right of browser: O usuário preenche o formulário e clica em Salvar

    browser->>server: POST [https://studies.cs.helsinki.fi/exampleapp/new_note_spa](https://studies.cs.helsinki.fi/exampleapp/new_note_spa)
 
    activate server
    server-->>browser: {"message":"note created"}

     Note right of browser:servidor devolve se foi ou nao adicionado

    server-->>browser:servidor devolve os dado adicionado {content: "teste spa", date: "2026-11-06T23:57:34.471Z"}
    deactivate server

    Note right of browser: O navegador  renderiza as notas com o novo item



```
