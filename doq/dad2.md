## Multi-Tier Modell Dash

```mermaid
sequenceDiagram
autonumber
    
    box Green User, Browser
    participant User-Agent
    end

    box lightblue Python & Libs
    participant Pandas
    participant Dash
    participant Plotly
    participant Flask
    end

    box gray Datenquellen
    participant CSV
    end
    
    User-Agent->>Flask: Anfrage URI
    Note over User-Agent, Flask: HTTP-Request
    
    Flask->>Dash: URI parsen
    Dash->>Pandas: Daten anfordern
    Pandas ->> CSV: Daten holen
    Pandas ->> Dash: Daten aufbereitet weiterleiten
    Pandas ->> Plotly: Charts/Plots erstellen
    Pandas ->> Flask: Webinhalte anfordern 
    Flask --> Flask: Generiere HTML, CSS, Javascript
    
    Flask->>User-Agent: Webinhalte liefern
    Note over User-Agent, Flask: HTTP-Request
    

   
   
```
