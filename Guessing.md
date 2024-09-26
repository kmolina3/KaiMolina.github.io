```mermaid
flowchart TD
    Start([Start]) --> Initialize[("Initialize Game")]
    Initialize --> GenerateNumber[("Generate Random Number\n(1 to 100)")]
    GenerateNumber --> UserInput[("Prompt User for Guess")]
    UserInput --> CheckInput{"Is Input Valid?"}
    CheckInput -->|No| InvalidInput[("Display Error: Please enter a number between 1 and 100")]
    InvalidInput --> UserInput
    CheckInput -->|Yes| EvaluateGuess[("Evaluate User Guess")]
    
    EvaluateGuess -->|Correct| CorrectGuess[("Display: Correct! You've guessed the number.")]
    EvaluateGuess -->|Too High| HighGuess[("Display: Too High! Try again.")]
    EvaluateGuess -->|Too Low| LowGuess[("Display: Too Low! Try again.")]
    
    CorrectGuess --> End([End])
    HighGuess --> UserInput
    LowGuess --> UserInput

