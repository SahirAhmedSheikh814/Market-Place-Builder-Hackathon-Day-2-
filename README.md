# Marketplace Builder Hackathon - Day 2

## Project Overview
This project represents the technical foundation of a scalable and user-friendly e-commerce platform, built as part of the Marketplace Builder Hackathon 2025. It integrates modern technologies to deliver a seamless shopping experience.

## Features
- **System Architecture:**
  - High-level design connecting frontend, backend, and third-party services.
  - Detailed workflows for user interactions.

- **API Endpoints:**
  - Comprehensive documentation for endpoints, methods, payloads, and responses.

- **Sanity CMS Integration:**
  - Schema designs for managing product, customer, and order data.

## System Architecture Diagram
The architecture integrates the following:
1. **Frontend (Next.js)**: A responsive and dynamic UI.
2. **Sanity CMS**: Backend for data management.
3. **Third-Party APIs**: Payment gateway (Stripe) and shipment tracking.

### Architecture Workflow:
1. User interacts with the frontend to browse, shop, and manage orders.
2. Frontend communicates with Sanity CMS for product and order data.
3. Payment and shipping services handled by Stripe and third-party APIs.

## API Endpoints
| **Endpoint**    | **Method** | **Purpose**                | **Payload**                                          | **Response Example**                                 |
| --------------- | ---------- | -------------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| `/products`     | GET        | Fetch all product details  | N/A                                                  | `{ "id": 1, "name": "Sofa", "price": 1000 }`         |
| `/cart`         | POST       | Add item to cart           | `{ "productId": 1, "quantity": 2 }`                  | `{ "cartId": 123, "status": "Added" }`               |
| `/checkout`     | POST       | Process checkout           | `{ "cartId": 123, "paymentInfo": {...}}`             | `{ "orderId": 456, "status": "Confirmed" }`          |

## Sanity CMS Schemas

### Product Schema:
```javascript
export default {
  name: 'product',
  type: 'document',
  fields: [
    { name: 'name', type: 'string', title: 'Product Name' },
    { name: 'price', type: 'number', title: 'Price' },
    { name: 'stock', type: 'number', title: 'Stock Level' },
    { name: 'image', type: 'image', title: 'Product Image' }
  ]
};
```

### Order Schema:
```javascript
export default {
  name: 'order',
  type: 'document',
  fields: [
    { name: 'customer', type: 'reference', to: [{ type: 'customer' }] },
    { name: 'products', type: 'array', of: [{ type: 'product' }] },
    { name: 'status', type: 'string', title: 'Order Status' }
  ]
};
```

## Workflows
### User Journey:
1. **Login/Signup**:
   - User registers or logs in.
   - Authenticated details are stored in Sanity CMS.

2. **Cart Management**:
   - Items added to the cart are tracked via APIs.

3. **Order Placement**:
   - Orders processed and stored in Sanity CMS, with payment handled by Stripe.

## Repository
The complete technical foundation, including diagrams and API documentation, is available here:
[GitHub Repository](https://github.com/SahirAhmedSheikh814/Market-Place-Builder-Hackathon-Day-2-.git)

## Next Steps
- Implement the documented workflows and architecture.
- Integrate advanced features like order tracking and stock management.

### Feedback
Feel free to open issues or contribute to the repository for enhancements.
