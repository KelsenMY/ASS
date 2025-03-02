
flowchart LR
    A((/octomap_full)):::topic -->|map| B(frontier_exploration)
    C((/detected_points)):::topic -->|lamp info| B
    B -->|/frontier_goal| D(Planner)
    E((/current_state_est)):::topic -->|pose & vel| D
    D -->|/planned_path| G((RViz / Debug))
    D -->|(goal / path)| F(waypoint_navigation)
    F -->|/trajectory| H((Flight Controller))

    classDef node fill:#fff,stroke:#333,stroke-width:1px,color:#000;
    classDef topic fill:#cfc,stroke:#090,stroke-width:1px,color:#000,stroke-dasharray: 5 5;

    class A,C,E,G,H topic
    class B,D,F node
