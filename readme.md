flowchart TD
    A[Customer selects items] --> B[Sales clerk enters sale in POS]
    B --> C{Payment method?}
    C --> D[Cash]
    C --> E[Credit card]

    D --> F[Accept cash and complete sale]
    F --> G[Record sale in system]

    E --> H[Send card for authorization]
    H --> I{Card approved?}
    I -->|Yes| J[Complete sale and issue receipt]
    J --> G[Record sale in system]
    I -->|No| K[Cancel sale and return items]

    %% End-of-day cash handling
    G --> L[End of day: Sales manager tallies cash]
    L --> M[Cashier prepares deposit ticket]
    M --> N[Courier transports deposit to bank]
    N --> O[Bank receives deposit]
