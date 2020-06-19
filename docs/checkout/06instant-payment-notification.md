---
tags: [Checkout]
---

# 03 - Instant Payment Notification (IPN)

After payment approval or decline an IPN is then sent to the merchant’s redirect URL to notify the merchant almost instantly about the payment status. Merchants can use this IPN to automate back-office and administrative functions, including automatically fulfilling orders and providing customers with order status.

The following values are submitted to the IPN redirect URL: "**checkout_id**", "**uuid**" and "**invoice_id**".


# Verify IPN

When the merchant receives the IPN they need to verify if it is valid. They would execute a POST request to "**/api/v1/merchant/verify_ipn**" with the "**checkout_id**", "**uuid**" and "**invoice_id**" values they received. If they receive a “200” response then it’s valid and if any other response code is received the message should explain what went wrong.