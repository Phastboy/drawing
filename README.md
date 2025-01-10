# drawing
Board

``` mermaid
classDiagram
    direction TB
    class App {
        +run()
        +handle_event()
        +quit()
    }

    class Screen {
        <<Abstract>>
        +draw()
        +handle_event()
    }

    class WelcomeScreen {
        +draw()
        +handle_event()
    }

    class ScreenFactory {
        +create_screen(screen_type: ScreenType): Screen
    }

    App --> ScreenFactory : Uses
    ScreenFactory --> Screen : Creates
    Screen <|-- WelcomeScreen : Implements
```

``` mermaid
graph TD
    A["`Mental Activity (Èrò)`"]
    B["`Language (Èdè)`"]
    C["`Speech (Òrò)`"]
    D["`Message (Àrokò)`"]
    A --> B
    B --> C
    C --> D
    
    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#cff,stroke:#333,stroke-width:2px
    style C fill:#fcf,stroke:#333,stroke-width:2px
    style D fill:#cfc,stroke:#333,stroke-width:2px
```
