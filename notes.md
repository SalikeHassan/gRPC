<img width="942" alt="image" src="https://github.com/user-attachments/assets/5cfd17a3-a4ff-4b61-828f-7183882e91b4" />

```proco
syntax = "proto3";

// Define the C# namespace
option csharp_namespace = "OrderManagement";

// Define a service
service OrderService {
  // RPC method to create an order
  rpc CreateOrder (OrderRequest) returns (OrderResponse);
}

// Message for the request
message OrderRequest {
  // Reserved fields (these cannot be reused for future properties)
  reserved 4, 5;                // Reserved sequence numbers
  reserved "oldFieldName";      // Reserved name

  int32 orderId = 1;            // Unique order ID
  string customerName = 2;      // Name of the customer
  repeated OrderItem items = 3; // List of items in the order
}

// Message for a single order item
message OrderItem {
  string productId = 1;        // Product ID
  int32 quantity = 2;          // Quantity of the product
}

// Message for the response
message OrderResponse {
  string status = 1;           // Status of the order
  string message = 2;          // Additional message
}
```
