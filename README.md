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
        +render_ui: RenderUI
        +handle_event(event: Event)
        +setup_ui(): void
    }

    class WelcomeScreen {
        +setup_ui()
        +handle_event(event: Event)
    }

    class RenderUI {
        +add_component(component: UIComponent)
        +remove_component(component: UIComponent)
        +handle_event(event: Event)
        +render()
    }

    class UIComponent {
        <<Abstract>>
        +render()
        +handle_event(event: Event)
    }

    class Button {
        +render()
        +handle_event(event: Event)
    }

    class Label {
        +render()
    }

    class ScreenManager {
        +set_default_screen(screen: Screen)
        +transition_to(screen_type: ScreenType)
        +get_current_screen(): Screen
        +handle_event(event: Event)
        +render_current_screen()
    }

    App --> ScreenManager : Manages
    ScreenManager --> Screen : Manages
    Screen --> RenderUI : Contains
    RenderUI --> UIComponent : Manages
    UIComponent <|-- Button : Implements
    UIComponent <|-- Label : Implements
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
