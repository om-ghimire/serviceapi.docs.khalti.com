# Khalti Staging  Services Data


## Testing Guidelines
- **Tokens**: Use the specified token (Test or LIVE) for each service.
- **Test Data**: Ensure test data matches the provided format (e.g., phone numbers, customer IDs) to avoid errors.
- **Multi-Step Services**: Follow the sequence of steps as required by the service (e.g., fetching details before payment).
- **Error Handling**: Test both success and failure scenarios where applicable (e.g., NTC Topup failed number).
- **Environment**: Always use the staging server for testing unless specified otherwise (e.g., SKY Cable uses LIVE server).

## Services


| Services Added for Testing | Server | TOKEN TO USE | Type | Online/Offline | Single/Multi Step | Test Data | Remarks |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| Khalti topup | Staging | Test | Topup | Online | single step | 9843576795, 9818154883, 9818136968 |  |
| ntc | Staging | LIVE | Topup | Online | single step | number : 9843007232 | Slab: 10 \-10000 |
| NTC Product | Staging | Live | package | online | multi step | number : 9840415403 |  |
| ncell | Staging | LIVE | Topup | Online | single step | Number : 9818722364 |  |
| Ncell product | Staging | TEST | data/voice pack | online | multi step | number : 9801856451 |  |
| Landline (PSTN) | Staging | LIVE | Topup | Online | single step | Number : 14232352 |  |
| Smartcell | Staging | LIVE | Topup | Online | single step | number: 9880123456 |  |
| Dishhome ERC | Staging | LIVE | ERC | Online | single step |  |  |
| Nepal Telecom ERC | Staging | LIVE | ERC | Online | single step |  |  |
| NEA                        | Staging | TEST         | Electricity | Online         | multi step        | counter: Bhaktapur dc <br> sc_no: 024.12.512, Consumer_id: 3042 <br> sc_no: 002.13.071, Consumer_id: 18795 <br> sc_no: 003.15.099, Consumer_id: 154, Office_code: 245:bhaktapur-dc <br> sc_no: 004.16.101, Consumer_id: 222, Office_code: 245:bhaktapur-dc <br> sc_no: 005.17.202, Consumer_id: 333, Office_code: 245:bhaktapur-dc <br> sc_no: 006.18.303, Consumer_id: 555, Office_code: 245:bhaktapur-dc | - Minimum amount a user can pay = payable_amount of oldest month <br> - 154: Rebate <br> - 222: Error / Multiple payment not allowed same day <br> - 333: Penalty <br> - 555: Normal User |
| Khanepani | Staging | TEST | Water | Online | multi step | customer\_code: 12, counter: 3123123:itahari-khanepani customer\_code:110011 counter:268:sandhikharka-khanepani |  |
| Dishhome | Staging | TEST | TV | Online | multi step | Cas id: 71909771942 |  |
| MeroTV | Staging | TEST | TV | Online | multi step | smart card id: 5000684178 |  |
| SIMTV Detail Fetch | Staging | Test | TV | Online | multi step | Customer Id : 1000159157 |  |
| SIMTV | Staging | LIVE | TV | Online | multi step | Customer Id : 1000159157 | Valid Amounts: \[300, 400, 500, 545, 550, 600, 750, 800, 875, 1000, 1050, 2000, 5000, 7000, 10000\] |
| Clear TV | Staging | Test | TV | Online | multi step | customer\_id:20180130070 number:9843576795 |  |
| Max TV | Staging | Test | TV | Online | multi step | customer\_id:0000405146 |  |
| Prabhu tv | Staging | Test | TV | TV | multi step | cas\_id:01234567891 amount : 350 |  |
| jagriti cable network | Staging | LIVE | TV | Offline | multi step | stb\_or\_cas\_id: 0123456789012345 |  |
| nijgadh | Staging | LIVE | TV | Offline | multi step | cas\_id:12345 smart\_card\_number:13415 box\_number:1234 |  |
| SKY TV | Staging | LIVE | TV | Online | multi step | customer\_id:1073661 stb:580143861 |  |
| Arrownet | Staging | TEST | ISP | Online | multi step | Username: Pradhanang |  |
| Techminds | Staging | TEST | ISP | Online | multi step | Request ID : 9824481540 |  |
| Worldlink | Staging | TEST | ISP | Online | multi step | Package Switchable Users : online\_renew Package switchable Users with Due payment : online\_due\_and\_package Package non switchable Users with Due payment : online\_due\_payment |  |
| Vianet | Staging | TEST | ISP | Online | multi step | Username : "9099" |  |
| Classitech | Staging | TEST | ISP | Online | multi step | Username : ctdeveloper |  |
| ADSL UL | Staging | LIVE | ISP | Online | single step | Number : 14232352 |  |
| Subisu | Staging | LIVE | ISP | Onlien | multi step | internet only khaltiinternet combo offer khaltioffer tv only paypoint\_video tv+internet khaltivideo |  |
| Websurfer | Staging | TEST | ISP | Online | multi step | customer\_id:1112858 |  |
| SKY Cable | LIVE (For now) | TEST | Internet | Online | multi step | customer\_id:1073661 username:ftth\_sujan\_thapa |  |
| Virtual Network | Staging | LIVE | Internet | Offline | single step | Username : khaltiUser |  |
| Web Network | Staging | LIVE | Internet | Offline | single step | Username : khaltiUser |  |
| Royal Network | Staging | LIVE | Internet | Offline | single step | Username : khaltiUser |  |
| East link | Staging | LIVE | Internet | Offline | single step | Username : khaltiUser |  |
| Alisha Communication | Staging | LIVE | Internet | Offline | multi step | Username : khaltiUser |  |
| Pokhara Internet | Staging | LIVE | Internet | Offline | single step | Username : khaltiUser |  |
| Ultranet | Staging | Test | Internet | Online | multi step | ultranet\_id:000044 |  |
| Infonet Communication | Staging | LIVE | Internet | Offline | multi step | Username : khaltiUser |  |
| Metrolink | Staging | LIVE | Internet | Offline | multi step | Username : khaltiUser |  |
| Tootle | Staging | TEST | Ride | Online | multi step | Number : 9841579738 |  |
| Midas | Staging | TEST | Education | Online | multi step | Number : 9843007232 |  |
| Kaspersky | Staging | LIVE | Antivirus | Online | multi step |  | (PLease use "Kaspersky Internet Security, 3-Users" |
| Sargarmatha Insurance | Staging | Test | Insurance | Online | multi step | debit\_note\_no: 001618/198500779 |  |
| Himalayan General Insurance | Staging | Test | Insurance | Online | multi step | policy\_no : KTM/MCY/11/18/19/95868 |  |
| NLG Insurance | Staging | Test | Insurance | Online | multi step | request\_id : 189943 | Service under Arhant, PLease search for Arhant in the docs |
| United Insurance | Staging | Test | Insurance | Online | multi step | request\_id : 189943 | Service under Arhant, PLease search for Arhant in the docs |
| Reliance Insurance | Staging | Test | Insurance | Online | multi step | policy\_no : 101000000008 dob:2018-09-26 |  |
| Premier Insurance | Staging | Test | Insurance | Offline | multi step | request\_id : 189944 | Service under Arhant, PLease search for Arhant in the docs |
| Prime Life Insurance | Staging | Test | Insurance | Online | multi step | policy\_no:1000002888 dob:2049-05-14 |  |
| Sanima Life Insurance | Staging | Test | Insurance | Online | multi step | "policy\_number": "2411232123", "date\_of\_birth": "1994-11-05" |  |
| Jyoti Life insurance | Staging | Test | Insurance | Online | multi step | policy\_no:6020000011 dob:2018-08-08 |  |
| Neco Insurance | Staging | LIVE | Insurance | offline | multi step | policy\_type:Fresh customer\_name:Ram lal policy\_category:Cattle & Crop amount:10 policy\_number:12 mobile\_number:9841111111 service\_name:neco-insurance insurance\_slug:neco-insurance |  |
| General Insurance | Staging | Test | Insurance | Online | multi step | request\_id : 189944 | Service under Arhant, PLease search for Arhant in the docs |
| Siddhartha Insurance | Staging | Test | Insurance | Online | multi step | request\_id : 189944 | Service under Arhant, PLease search for Arhant in the docs |
| Sanima General Insurance | Staging | Test | Insurance | Online | multi step | request\_id : 189944 insurance\_slug:sanima-general-insurance | Service under Arhant, PLease search for Arhant in the docs |
| Union Life Insurance | Staging | Test | Insurance | Online | multi step | policy\_no:2010000027 dob:2030-01-01 |  |
| Surya Life Insurance | Staging | Test | Insurance | Online | multi step | policy\_no:207001096 dob:2012-08-05 |  |
| Nepal Life Insurance | Staging | Test | Insurance | Online | multi step | policy\_no:401059698 dob:2008-03-20 |  |
| Mahalaxmi Life Insurance | Staging | Test | Insurance | Online | multi step | dob:1995-04-24 policy\_no:9010000033 |  |
| Shikhar Insurance | Staging | LIVE | Insurance | Offline | multi step | customer\_name:Babu Bhaiyaa address:Thimi contact\_number:9851168561 email:babubaiyaa@gmail.com policy\_type:new policy\_number:oatusatnuha amount:1000 branch:Pokhara policy\_description:it's ok policy\_name:Covid 19 insurance |  |
| National Life Insurance | Staging | Test | Insurance | online | multi step | policy\_no:500002814 dob:1985-12-02 |  |
| Surya Life Insurance first payment | Staging | Test | Insurance | online | multi step | porformance/policy no : 510001039 |  |
| Ime General Insurance | Staging | LIVE | Insurance | Offline | multi step | policy\_type:Endorsement insurance\_type:Property Insurance branch:Pokhara full\_name:test test address:test test mobile\_number:9841111111 policy\_description:est tet debit\_note\_no:123465789 bill\_no:12346589 email:ressrew@gmail.com amount:10 |  |
| Flight | staging | LIVE | Flight | online | multi step | KTM \- Pokhara for future days ( preferably more than a month ) |  |
| Echalan | staging | Test | government payment | online | multi step | app\_id:MER-7-APP-10 voucher\_no:2078-2325038 service:echalan fiscal\_year:7778 additional voucher number : "2077-3773940", "2077-3773941", "2077-3773942", "2077-3773943" | app\_id for prod : GON-7-TVRS-1 |
| Sagarmatha Insurance | staging | Test | Insurance | offline | multi step | debit\_note\_no: 001618/198500779 |  |
| Prudential Insurance | staging | LIVE | Insurance | offline | multi step | amount:1200 issue\_branch:Kathmandu customer\_name:Babu rao mobile\_number:9800000000 email:baburao@gmail.com debit\_note\_or\_bill\_number:123456 |  |
| IME Life Insurance | staging | TEST | Insurance | online | multi step | policy\_no:101000315 dob:1976-09-22 |  |
| NT FTTH | staging | LIVE | ISP | online | single step | number : 10000111111111 |  |
| Nijgadh Cable | staging | LIVE | TV / ISP | online | multi step |  |  |
| Everest Wireless | staging | LIVE | ISP | online | multi step |  |  |
| bbn internet | staging | TEST | ISP | online | multi step | username : pnt\_test |  |
| Dolfin net | staging | LIVE | ISP | offline | multi step |  |  |
| times vendor | staging | TEST | ISP | online | multi step |  |  |
| Infonet Technology | staging | TEST | ISP | online | multi step |  |  |
| Broadlink | staging | TEST | ISP | online | multi step | Outstanding user : 53905 , outstanding Package user : 47531 |  |
| PnG | staging | LIVE | ISP \+TV | online | multi step | \<user\_name should be. in format 0000XXXXXX or XXXXXX\> |  |
| GRS Internet | staging | TEST | ISP | online | multi step | username:blya-test |  |
| Loop network | staging | TEST | ISP | online | multi step | username : new, active, expired |  |
| hashcnet v2 | staging | TEST | ISP | online | multi step | username : jeetenaug4 |  |
| Prime Life Insurance | staging | TEST | Insurance | online | multi step | "policy\_no":"1000002888", "dob":"2049-05-14", |  |
| Asian Life Insurance | staging | TEST | Insurance | online | multi step | policy\_no:51080000258 dob\_year:1984 |  |
| Minion Bank Withdraw |  |  |  |  |  | All txn will be success ... will be failed for account number starting from 400 |  |
| VRS | staging | TEST | gov payment | online | multistep | "license\_type": "Zonal", "province\_id": "3", "zone": "बा", "vehicle\_symbol": "प", "lot\_no": "76", "vehicle\_number": "4466", "vehicle\_type": "2", "tax\_office\_id": "17" |  |
| RC card \- recharge card \- dishhome erc | staging | LIVE | RC card | offline | single | Valid amount dishhome-erc: 500, 1000, 2000, 3000, 4000, 5000, 6000, 7000, 9000, 10000 |  |
| VNS | staging | TEST | ISP | online | multistep |  |  |
| Rapid Unique Net | staging | TEST | ISP | online | multistep | username \- testuser |  |
| Rastriya Beema Sanstha | staging | TEST | Insurance | online | multistep | reference:{{$guid}} token:{{TEST Secret Key}} policy\_no:49726 dob:1962-08-10 |  |
| Surya Joyti DOFE | staging | Live | Dofe | online | multistep | { "plancode": "81", "dob": "1998-02-21", "proDate": "2023-12-14", "sumAssured": "1000000", "termYear": "2", "termMonth": "6" } |  |
| Nepal Insurance | staging | LIVE | Insurance | online | multistep | policy\_type:1 branch:1 insurance\_type:1 amount:1000 debit\_note\_number:11111 customer\_name:Babu Bhaiyaa customer\_address:Thimi mobile\_number:9851168561 policy\_description:11111 bill\_no:11111 email:babubaiyaa@gmail.com token:{{Live Token}} reference:{{$guid}} |  |
| Wifi Nepal | staging | LIVE | ISP | online | multistep | username:test10\_wifinepal |  |
| Dishhome | staging | LIVE | TV/ISP | online | multistep | casid:-13830459 13830305 13830252 13830029 |  |
| KUKL | staging | LIVE | Khanepani | online | multistep | counter 1114:test-kukl BILL: 1114008815, 1114013895, 1114002067 |  |
