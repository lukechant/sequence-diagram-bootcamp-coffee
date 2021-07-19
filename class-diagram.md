classDiagram
        class Customer{
            +sendOrder()
            +payOrder()
            +receiveOrderConfirmation()
        }
        class CoffeeShop {
            +List<Order> orders
            +receiveOrder()
            +makeCoffee()
            +updateOrderStatus(order)
        }
        class Order{
            +Coffee coffee
            +int total
            +isReady() bool
        }
        class Coffee {
            LATTE
            AMERICANO
            FRAPPE
        }

        class User {
            +String email
            +String username
            +String password
        }
        <<Interface>> User
        <<Enumeration>> Coffee

        User --|> Customer
        User --|> CoffeeShop
        class CheckoutSession {
            +Order order
            +List<String> paymentDetails
            +int amount
            +requestPaymentAuthorisation(paymentDetails) bool
            +updateOrderStatus(order)
            +finaliseOrder(order)
        }
