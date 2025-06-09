
# Sector Codes

| City | Code |
|------|------|
| Bhadrapur | BDP |
| Bhairahawa | BWA |
| Bharatpur | BHR |
| Biratnagar | BIR |
| Dhangadi | DHI |
| Illam | ILM |
| Janakpur | JKR |
| Jomsom | JMO |
| Kathmandu | KTM |
| Lukla | LUA |
| Rajbiraj | RJB |
| Ramechhap | RCH |
| Mountain | MTN |
| Nepalgunj | KEP |
| Pokhara | PKR |
| Simara | SIF |
| Simikot | IMK |
| Tumlingtar | TMI |
| Surkhet | SKH |
| Varanasi | VNS |

## Overview

The Sector Codes section lists the airport codes for cities supported by the flight APIs. These codes are used in the Flight Search and Flight Status APIs to specify origin and destination sectors.

# Short Name of Airlines

| Airline | Code |
|---------|------|
| Buddha Air | U4 |
| Yeti Airlines | YT |
| Tara Air | RMK |
| Shree Airlines | SHA |
| Saurya Airlines | S1 |
| Guna Airlines | GUA |

## Overview

The Short Name of Airlines section provides the airline codes and their corresponding names used across the flight APIs for identifying airlines in search, booking, and status responses.

# Aircraft Type

| Aircraft | Description |
|----------|-------------|
| Beech18 | 18 seater (operated by Guna and Buddha Air) |
| J41 | Jetstream, 28 seater (operated by Guna) |
| ATR42 | 45 seater (operated by Buddha Air) |
| ATR72 | 72 seater (operated by Yeti and Buddha Air) |
| CRJ200 | 50 seater (operated by Saurya and Shree Airlines) |
| CRJ700 | 70 seater (operated by Shree Airlines) |
| Dash Q400 | 80 seater (operated by Shree Airlines) |
| Tw | 18 seater (operated by Tara Air) |

**Note:** Additional aircraft types will be added if new aircraft are introduced by airlines.

## Overview

The Aircraft Type section lists the types of aircraft used by airlines in the flight APIs, including their seating capacity and operating airlines. This information is included in flight search and issue responses.

# Commission Calculation Process

There are two types of account commission calculation:

1. **Reseller Account**
2. **Normal Account**

Flight API is always used by Normal Accounts. Reseller Accounts are those that have access to create multiple Normal Accounts under them, add services, and set commissions.

## For Normal Account

The commission is provided as per the contract.

**Example:**
- As per contract, 80% commission is provided.
- For a flight transaction with a total commission of 200, a Normal Account receives 80%, i.e., Rs. 160.

## For Reseller Account

The commission is calculated based on two accounts: the Reseller Account and the Normal Account. The commission is determined using the base amount.

**Example:**
- As per contract, 80% commission is provided to the Reseller.
- The Reseller Account creates a Normal Account (e.g., ABC Account) and sets its commission to 60%.
- Transactions are always initiated by the Normal Account (ABC Account).
- For a flight transaction with a total commission of 200:
  - Normal Account (ABC Account) receives 60%, i.e., Rs. 120.
  - Reseller Account receives 80% - 60% = 20%, i.e., Rs. 40.

**Note:** Reseller Accounts cannot set a commission for Normal Accounts higher than their own commission. The commission for a Normal Account must be less than or equal to the Reseller Account’s commission (e.g., if the Reseller gets 80%, they cannot set 81% for the Normal Account).

## Overview

The Commission Calculation Process outlines how commissions are distributed for flight transactions. Normal Accounts receive commissions as per contract, while Reseller Accounts can create Normal Accounts and set their commissions, with the Reseller earning the difference between their contracted commission and the Normal Account’s commission.