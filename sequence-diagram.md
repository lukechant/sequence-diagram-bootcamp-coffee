activate Customer
    Customer->>App: open app
    deactivate Customer
    activate App
    App-->>Customer: menu "list of items"
    deactivate App
    activate Customer
    Customer->>App: sends order
    deactivate  Customer
    activate App
    App-->>Customer: requests payment
    activate Customer
    deactivate App
    Customer-->>App: makes payment
    deactivate Customer
    activate App
    App->>Bank: requests payment authorization
    activate  Bank
    Bank-->>App: sends positive payment authorization
    deactivate  Bank
    App-->>+Customer: sends confirmation 
    activate  Customer
    App->>+CoffeeShop: sends order 
    activate  CoffeeShop
    CoffeeShop->>+CoffeeShop: make coffee 
    CoffeeShop-->>App: sends notification "coffee is ready"
    deactivate  CoffeeShop 
    App-->>+Customer: sends notification "coffee is ready"
    deactivate App
    Customer->>+CoffeeShop: collects coffee
