# Dishhome Go Coupon

This service sells Dishhome Go coupons. After a successful payment the API returns the coupon code (PIN/serial). Integrators should send the PIN to the end customer via SMS and email.

**SMS content suggestion:**

- Your Dishhome Go coupon: `{{pin}}` (Serial: `{{serial}}`). Thank you for your purchase.

**Email content suggestion:**

- Subject: Your Dishhome Go Coupon
- Body: Your Dishhome Go coupon PIN is `{{pin}}` and serial is `{{serial}}`. Keep it safe.

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
 