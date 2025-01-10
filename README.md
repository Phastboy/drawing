# drawing
Board

``` mermaid
classDiagram
    direction TB

    class App {
        -running: bool
        -current_screen: Screen
        +run()
        +handle_event()
        +quit()
        +get_instance() App
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

    %% Singleton Pattern
    App <-- App : "Static Instance Access"

```
