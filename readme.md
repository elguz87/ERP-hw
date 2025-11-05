```mermaid
graph LR

  %% CUSTOMER
  subgraph Customer
    A[Selects items to purchase]
  end

  %% SALES CLERK
  subgraph Sales_Clerk
    B[Receives items from customer]
    C[Enters sale in POS system]
    D[Prompts for payment method]
    E{Payment type?}
    F[Accept cash]
    G[Submit card for authorization]
    H{Card approved?}
    I[Complete sale & issue receipt]
    J[Cancel sale & return items]
  end

  %% SALES MANAGER
  subgraph Sales_Manager
    K[Tallies cash end of day]
    L[Bundles cash for cashier]
  end

  %% CASHIER
  subgraph Cashier
    M[Receives cash from manager]
    N[Prepares bank deposit ticket]
    O[Hands deposit to courier]
  end

  %% COURIER
  subgraph Courier
    P[Transports deposit to bank]
  end

  %% BANK
  subgraph Bank
    Q[Bank accepts deposit]
  end

  %% FLOW
  A --> B --> C --> D --> E
  E -->|Cash| F --> K
  E -->|Credit card| G --> H
  H -->|Yes| I --> K
  H -->|No| J --> K
  K --> L --> M --> N --> O --> P --> Q
