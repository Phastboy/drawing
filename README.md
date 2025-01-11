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

    class ScreenManager {
        +transition_to(screen_type: ScreenType)
        +render_current_screen()
        +transition(action: TransitionAction)
        +history: List~ScreenState~
        +current: ScreenState
    }

    class Screen {
        +render_ui: RenderUI
        +state_manager: StateManager
        +state: ScreenState
        +setup_ui(): void
    }

    class ScreenState {
        +active: boolean
        +event: Event
    }

    class RenderUI {
        +add_component(component: UIComponent)
        +remove_component(component: UIComponent)
        +handle_event(event: Event)
        +render()
        +layout_manager: LayoutManager
        +animation_manager: AnimationManager
    }

    class StateManager {
        +set_state(key, value)
        +get_state(key)
        +subscribe(listener)
    }

    class TransitionAction {
        <<Enum>>
        +Next
        +Previous
    }

    App --> ScreenManager : Singleton
    ScreenManager --> Screen : Manages
    Screen --> ScreenState : Contains
    Screen --> RenderUI : Contains
    Screen --> StateManager : Observes
    RenderUI --> LayoutManager : Uses
    RenderUI --> AnimationManager : Uses
    RenderUI --> UIComponent : Manages
    UIComponent <|-- Button : Implements
    UIComponent <|-- Label : Implements
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
