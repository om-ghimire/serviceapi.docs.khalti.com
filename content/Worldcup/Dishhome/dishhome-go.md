# Dishhome Go Coupon

This service sells Dishhome Go coupons. After a successful payment, the API returns the coupon code (PIN/serial). Integrators should send the PIN to the end customer via SMS and email.

**SMS content suggestion**

- Thank you for subscribing to Dishhome Go via Khalti. Your coupon code is `{pin}`. Redeem it in the DGO app. T&C apply.

**Email content suggestion**

- **Subject:** Purchase Confirmation — DGO Coupon Code

- **Body:**

  Dear User,

  Thank you for subscribing to the DGO coupon through Khalti.

  **Your Coupon Code:** `{pin}`

  To redeem your coupon, please apply the code within the DGO app.

  Please note:

  - Coupons are valid only in the region where they are issued.
  - Coupon validity and applicable terms are governed by DGO.

  If you need any assistance, please contact our support team.

  Best regards,  
  {Company name}

---

### 1. List Products
This API returns available Dishhome Go coupon products.

**GET**  
`{{base_url}}/api/products/dishhome-go-coupon/?token={{token}}`

#### Response

<pre><code class="json">
{
  "status": true,
  "data": [
    {
      "idx": "d5LdSJWcwcYWLQrLcN8dEu",
      "name": "Fifa-2026",
      "value": "fifa-2026",
      "amount": 100.0
    }
  ]
}
</code></pre>

---

### 2. Payment
This endpoint processes the payment and returns the coupon PIN/serial.

**POST**  
`{{base_url}}/api/use/dishhome-go-coupon/`

#### Request Body

<pre><code class="json">
{
  "token": "{{token}}",
  "reference": "{{$guid}}",
  "name": "Dishhome test",
  "value": "web",
  "amount": 100,
  "phone_number": 9860848045,
  "email": "a@gmail.com"
}
</code></pre>

#### Response

<pre><code class="json">
{
  "status": true,
  "state": "Success",
  "message": "Your Pin number is 'c3'",
  "serial": "c3",
  "pin": "c3",
  "credits_consumed": 100.0,
  "credits_available": 99988811133.2798,
  "id": 176925
}
</code></pre>

}
 