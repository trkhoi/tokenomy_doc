# tokenomy_doc
Document for Tokenomy's APIs

# APIs using in loyalty screen
## API login
### Account
`dwarves@tokenomy.com`
### Reponse
```json
{
    "success": 1,
    "return": {
        "key": "LDNZOO9K-Q0VTRSQN-YJ8I7MHO-ZPLLHLMU-IO0ASXAZ",
        "secret": "e40ca69b1b659c9e8ad2988e7dd6711f8957a5925afec073ae97036e56019eeadb157003814ff597",
        "app_token": {
            "earn_token": "2efb4a3cb171d8e4dc4bc5cbe81e65b4d1d58d6c28aabafb5f92dd58b74f7450624b74e61c6895ac"
        },
        "expired": 1617860937
    }
}
```
## API get user info
### Domain
`https://uat-earn-api.tokenomy.com`
### Endpoint:
`GET /api/v1/user/info`
### Change: 
- Now this API return 1 more field `loyalty_tier`
### Response: 
```json
{
    "email": "dwarves@tokenomy.com",
    "gauth_enabled": false,
    "is_indodax_login": true,
    "is_premium": false,
    "is_verified": true,
    "language": "en",
    "last_name": "DF",
    "loyalty_tier": "silver",
    "name": "Dwarf",
    "phone": "84793257885",
    "ticket_collected": 65,
    "tokenomy_user_id": 396,
    "username": ""
}
```
## API show balance of user 
### Domain
`https://api.uat.tokenomy.com`
### Endpoint
`GET /v2/user/balance`
### Request
Headers:
- `token`: `earn_token` from API login
- `app-id`: value is `3043976`
- `secret`: 
### Response
```json
{
    "success": 1,
    "return": {
        "balance": {
            "btc": "2",
            "eth": "999.9969",
            "idk": "56169.6875",
            "ten": "97650.94109589",
            "xtz": "735.78125"
        },
        "balance_hold": {
            "idk": "43441.3125"
        },
        "address": {
            "act": "",
            "bal": "0x7237ba2a8eaee2da3b861003823401d5fb55e5f0",
            "bch": "",
            "bchabc": "",
            "bnb": "bnb1u8tv2fpcd3fz7yn9jcpqr2vd5suhpx6gyx54n7",
            "btc": "",
            "cmt": "",
            "comp": "0x7237ba2a8eaee2da3b861003823401d5fb55e5f0",
            "dai": "0x7237ba2a8eaee2da3b861003823401d5fb55e5f0",
            "eos": "tokexaccount",
            "etc": "",
            "eth": "0x7237ba2a8eaee2da3b861003823401d5fb55e5f0",
            "hart": "0x7237ba2a8eaee2da3b861003823401d5fb55e5f0",
            "hnst": "bnb1u8tv2fpcd3fz7yn9jcpqr2vd5suhpx6gyx54n7",
            "idk": "0x7237ba2a8eaee2da3b861003823401d5fb55e5f0",
            "inx": "0x7237ba2a8eaee2da3b861003823401d5fb55e5f0",
            "knc": "0x7237ba2a8eaee2da3b861003823401d5fb55e5f0",
            "link": "0x7237ba2a8eaee2da3b861003823401d5fb55e5f0",
            "lrc": "0x7237ba2a8eaee2da3b861003823401d5fb55e5f0",
            "ltc": "",
            "lyfe": "0x7237ba2a8eaee2da3b861003823401d5fb55e5f0",
            "lyfebep": "bnb1u8tv2fpcd3fz7yn9jcpqr2vd5suhpx6gyx54n7",
            "mkr": "0x7237ba2a8eaee2da3b861003823401d5fb55e5f0",
            "neo": "",
            "ont": "",
            "pxg": "0x7237ba2a8eaee2da3b861003823401d5fb55e5f0",
            "scc": "0x7237ba2a8eaee2da3b861003823401d5fb55e5f0",
            "six": "GC3UVRVE54GJ45YTOPPYI4TTH2ZN4CZLVIHZNJ5PR5GP54IF6B5KEY5B",
            "snx": "0x7237ba2a8eaee2da3b861003823401d5fb55e5f0",
            "swipe": "bnb1u8tv2fpcd3fz7yn9jcpqr2vd5suhpx6gyx54n7",
            "ten": "0x7237ba2a8eaee2da3b861003823401d5fb55e5f0",
            "trx": "",
            "usdc": "0x7237ba2a8eaee2da3b861003823401d5fb55e5f0",
            "usdt": "0x7237ba2a8eaee2da3b861003823401d5fb55e5f0",
            "vex": "tokenomyvexa",
            "xlm": "GDZTTWVR6DDDVOUM33JBWOWFN4UHVHBYYF7LKM5S25VCHNTCRSP45WKU",
            "xlp": "0x7237ba2a8eaee2da3b861003823401d5fb55e5f0",
            "xmr": "",
            "xtz": "",
            "zec": ""
        },
        "server_time": 1617776212
    }
}
```

# APIs for loyalty flow
## API show loyalty tier
### Domain
`https://uat-earn-api.tokenomy.com`
### Endpoint
`GET /api/v1/user/loyalty`
### Request
Headers:
- `Key`: `key` in API login
- `tokenomy_uat_earn_token`: `earn_token` from API login
### Response
```json
{
    "data": [
        {
            "apy_bonus": 0,
            "customer_support": "Standard",
            "id": "bronze",
            "investor_oriented_newsletter": ".",
            "is_upgradable": true,
            "loan_ratio": {
                "idk": 1,
                "ten": 0.1
            },
            "logo": "bronze.svg",
            "min_btc_value": 0,
            "min_ten_lock": 0,
            "name": "Bronze",
            "reporting": "Standard",
            "user_interface": "Standard"
        },
        {
            "apy_bonus": 0.5,
            "customer_support": "Standard",
            "id": "silver",
            "investor_oriented_newsletter": ".",
            "is_upgradable": true,
            "loan_ratio": {
                "idk": 1,
                "ten": 0.1
            },
            "logo": "gold.svg",
            "min_btc_value": 0,
            "min_ten_lock": 1000,
            "name": "Silver",
            "reporting": "Standard",
            "user_interface": "Standard"
        },
        {
            "apy_bonus": 1,
            "customer_support": "Standard",
            "id": "gold",
            "investor_oriented_newsletter": ".",
            "is_upgradable": false,
            "loan_ratio": {
                "idk": 1,
                "ten": 0.1
            },
            "logo": "gold.svg",
            "min_btc_value": 0,
            "min_ten_lock": 500000,
            "name": "Gold",
            "reporting": "Standard",
            "user_interface": "Standard"
        },
        {
            "apy_bonus": 1,
            "customer_support": "Dedicated officier with private WhatsApp channel",
            "id": "premium",
            "investor_oriented_newsletter": "Monthly, includes top crypto stories & market updates",
            "is_upgradable": true,
            "loan_ratio": {
                "idk": 1,
                "ten": 0.1
            },
            "logo": "premium.svg",
            "min_btc_value": 1,
            "min_ten_lock": 10000,
            "name": "Premium",
            "reporting": "Monthly statements & annual performance review",
            "user_interface": "Premium interface"
        }
    ]
}
```

## API upgrade loyalty tier
### Domain
`https://uat-earn-api.tokenomy.com`
### Endpoint
`POST /api/v1/user/loyalty`
### Request
Headers:
- `Key`: `key` in API login
- `tokenomy_uat_earn_token`: `earn_token` from API login
Body:
- 4 types of loyalty: `bronze`, `silver`, `gold`, `premium`
```json
{
    "loyalty_id": "silver"
}
```
### Response
- Case 1: TEN balance is enough to upgrade
```json
{
    "data": {
        "avatar": null,
        "email": "dwarves@tokenomy.com",
        "full_name": null,
        "gauth_enabled": false,
        "id": 42,
        "is_indodax_login": true,
        "is_premium": false,
        "is_verified": true,
        "language": "en",
        "loyalty_tier": "silver",
        "name": "Dwarf",
        "phone": "84793257885",
        "role": null,
        "ticket_collected": 65,
        "tokenomy_user_id": 396,
        "username": ""
    }
}
```
- Case 2: TEN balance is not enough to upgrade
```json
{
    "error": {
        "code": 400,
        "message": "TEN balance not enough to upgrade or migrate server down"
    }
}
```