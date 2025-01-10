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
        +render()
        +handle_event()
    }

    class WelcomeScreen {
        +render()
        +handle_event()
    }

    class ScreenFactory {
        +create_screen(screen_type: ScreenType): Screen
    }

    App --> ScreenFactory : Uses
    ScreenFactory --> Screen : Creates
    Screen <|-- WelcomeScreen : Implements
```
