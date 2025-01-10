# drawing
Board

``` mermaid
classDiagram
    direction TB
    class App {
        +run()
        +handle_event(event: Event)
        +quit()
    }

    class Screen {
        <<Abstract>>
        +draw()
        +handle_event(event: Event)
        +on_exit(): Event
    }

    class WelcomeScreen {
        +draw()
        +handle_event(event: Event)
    }

    class ScreenManager {
        +set_default_screen(screen: Screen)
        +transition_to(screen_type: ScreenType)
        +get_current_screen(): Screen
        +handle_event(event: Event)
        +draw_current_screen()
    }

    class ScreenFactory {
        +create_screen(screen_type: ScreenType): Screen
    }

    App --> ScreenManager : Manages
    ScreenManager --> ScreenFactory : Uses
    ScreenManager --> Screen : Manages
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
