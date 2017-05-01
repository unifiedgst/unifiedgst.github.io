---
title: API Reference

language_tabs:
  - JSON

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to Unified GST Developer Portal. This portal is intended for developer community. Specifications releated to Unified GST APIs will be available through this portal. This portal will also host sample code, public keys and sandbox information and will be a one stop shop for developer's, who wanted to build innovative application for Tax payers.

You can add automatic realtime transactional invoice filing, ledger management, tax returns filing and compliance management to your software using the UnifiedGST API.

# Authentication

> To authorize, use this code:

This API is invoked by the GSP application to issue authentication token by verifying username and OTP combination.

```JSON
{
  "action": "AUTHTOKEN",
  "username": "AkashSingh01",
  "app_key": "48Kw7zR3L9nsbBJI3BJBmg8K0cx/XoGzR6uJHcBCuEPUlBTDPLochguhJk1DTvvHYQqQwaU0yhOqfZHgalD9sGMikaEBmY7Y1YcjP5drvwhmmcqQmCLK3D1FE18ditvlqV4DWou5feLM07QwWTj/i8mDwc5YgWz0cYnr6r7wnd2nlbmMxdHOYbKjOP6SxOdD2Gb6GZDI5+RFkkfGSPKwtvXR9NfZQaLaTIY1w8O0X0NI56C9oqjcqT5+FgdpTnLYc3rodHJuEFVgqfeTpWSk3QfAcnQg9P1N9Azcx2OI+AXbLLhcLLbSpfveelhaK02uEdUDYgGHfztr//9RPfqOzg==",
  "otp": "BmgX0cZuroBbOHk7KT4Wzw=="
}
```

> The above command returns JSON structured like this:

```json
{
  "status_cd": "1",
  "auth_token": "1ac094d572934070b193683054c1f5ba",
  "expiry": 120,
  "sek": "xyGEm6ZwaCK8m3A7gaQODOcb7cCYBOo/tqa6XTysvH+H3YvUBbtcgT4xd4qfCspP"
}
```

### HTTP Request

`POST https://unifiedgst.com/taxpayerapi/v0.2/authenticate/`

<aside class="notice">
You must replace <code>app_key</code> with your personal API key.
</aside>

# GST Returns

## GSTR1

This API is used to save entire GSTR1 invoices.

```JSON
{
  "gstin": "27AHQPA7588L1ZJ",
  "fp": "122016",
  "gt": 3782969.01,
  "b2b": [
    {
      "ctin": "01AABCE2207R1Z5",
      "inv": [
        {
          "inum": "S008400",
          "idt": "24-11-2016",
          "val": 729248.16,
          "pos": "06",
          "rchrg": "N",
          "prs": "Y",
          "od_num": "DR008400",
          "od_dt": "20-11-2016",
          "etin": "01AABCE5507R1Z4",
          "itms": [
            {
              "num": 1,
              "itm_det": {
                "ty": "G",
                "hsn_sc": "G1221",
                "txval": 10000,
                "irt": 3,
                "iamt": 833.33,
                "crt": 4,
                "camt": 500,
                "srt": 5,
                "samt": 900,
                "csrt": 2,
                "csamt": 500
              }
            }
          ]
        }
      ]
    }
  ],
  "b2ba": [
    {
      "ctin": "01AABCE2207R1Z5",
      "inv": [
        {
          "oinum": "S008400",
          "oidt": "24-11-2016",
          "inum": "S008400",
          "idt": "24-11-2016",
          "val": 729248.16,
          "pos": "06",
          "rchrg": "N",
          "prs": "Y",
          "od_num": "DR008400",
          "od_dt": "20-11-2016",
          "etin": "01AABCE5507R1Z4",
          "itms": [
            {
              "num": 1,
              "itm_det": {
                "ty": "G",
                "hsn_sc": "G1221",
                "txval": 10000,
                "irt": 3,
                "iamt": 833.33,
                "crt": 4,
                "camt": 500,
                "srt": 5,
                "samt": 900,
                "csrt": 2,
                "csamt": 500
              }
            }
          ]
        }
      ]
    }
  ],
  "b2cl": [
    {
      "state_cd": "05",
      "inv": [
        {
          "cname": "R_Glasswork Enterprise",
          "inum": "B129840",
          "idt": "14-04-2016",
          "val": 1000.03,
          "pos": "06",
          "prs": "Y",
          "od_num": "DR008400",
          "od_dt": "20-11-2016",
          "etin": "27AHQPA8875L1ZU",
          "itms": [
            {
              "num": 1,
              "itm_det": {
                "ty": "S",
                "hsn_sc": "S249",
                "txval": 10000,
                "irt": 3,
                "iamt": 833.33,
                "csrt": 2,
                "csamt": 500
              }
            }
          ]
        }
      ]
    }
  ],
  "b2cla": [
    {
      "state_cd": "05",
      "inv": [
        {
          "oinum": "9266",
          "oidt": "10-02-2016",
          "cname": "Glass store shop",
          "inum": "92661",
          "idt": "10-01-2016",
          "val": 784586.33,
          "pos": "01",
          "prs": "N",
          "od_num": "DR008400",
          "od_dt": "20-11-2016",
          "etin": "27AHQPA8875L1ZU",
          "itms": [
            {
              "num": 1,
              "itm_det": {
                "ty": "S",
                "hsn_sc": "S2469",
                "txval": 10000,
                "irt": 3,
                "iamt": 833.33,
                "csrt": 2,
                "csamt": 500
              }
            }
          ]
        }
      ]
    }
  ],
  "b2cs": [
    {
      "state_cd": "05",
      "ty": "G",
      "hsn_sc": "G2469",
      "txval": 10000,
      "irt": 3,
      "iamt": 500,
      "crt": 4,
      "camt": 500,
      "srt": 5,
      "samt": 900,
      "csrt": 3,
      "csamt": 833,
      "prs": "Y",
      "od_num": "DR008400",
      "od_dt": "20-11-2016",
      "etin": "20ABCDE7588L1ZJ",
      "typ": "E"
    }
  ],
  "b2csa": [
    {
      "omon": "122016",
      "oty": "S",
      "ohsn_sc": "S2811",
      "osupst_cd": "05",
      "ty": "G",
      "hsn_sc": "G811",
      "state_cd": "05",
      "txval": 10000,
      "irt": 3,
      "iamt": 500,
      "crt": 4,
      "camt": 500,
      "srt": 5,
      "samt": 900,
      "csrt": 3,
      "csamt": 833,
      "prs": "Y",
      "od_num": "DR008400",
      "od_dt": "20-11-2016",
      "etin": "20ABCDE7588L1ZJ",
      "typ": "E"
    }
  ],
  "cdnr": [
    {
      "ctin": "01AAAAP1208Q1ZS",
      "nt": [
        {
          "ntty": "C",
          "nt_num": "533515",
          "nt_dt": "23-09-2016",
          "rsn": "Not mentioned",
          "inum": "915914",
          "idt": "23-09-2016",
          "rchrg": "N",
          "val": 10000,
          "irt": 3,
          "iamt": 833.33,
          "crt": 4,
          "camt": 500,
          "srt": 5,
          "samt": 900,
          "csrt": 2,
          "csamt": 500,
          "etin": "01AAAAP1208Q1Z7"
        }
      ]
    }
  ],
  "cdnra": [
    {
      "ctin": "01AAAAP1208Q1ZS",
      "nt": [
        {
          "ntty": "C",
          "rsn": "Not mentioned",
          "ont_num": "533515",
          "ont_dt": "23-09-2016",
          "nt_num": "533515",
          "nt_dt": "23-09-2016",
          "inum": "915914",
          "idt": "23-09-2016",
          "rchrg": "N",
          "val": 5225.28,
          "irt": 3,
          "iamt": 833.33,
          "crt": 4,
          "camt": 500,
          "srt": 5,
          "samt": 900,
          "csrt": 2,
          "csamt": 500,
          "etin": "01AAAAP1208Q1Z7"
        }
      ]
    }
  ],
  "at": [
    {
      "typ": "B2B",
      "cpty": "12DEFPS5555D1Z2",
      "state_cd": "12",
      "doc_num": "100001",
      "doc_dt": "10-03-2016",
      "itms": [
        {
          "ty": "S",
          "hsn_sc": "S9043",
          "ad_amt": 100,
          "irt": 3,
          "iamt": 833.33,
          "crt": 4,
          "camt": 500,
          "srt": 5,
          "samt": 900,
          "csrt": 2,
          "csamt": 500
        }
      ]
    }
  ],
  "ata": [
    {
      "typ": "B2B",
      "ocpty": "R_Glasswork Enterprise",
      "odoc_num": "A100001",
      "odoc_dt": "10-03-2016",
      "cpty": "Glasswork Enterprise",
      "state_cd": "12",
      "doc_num": "100001",
      "doc_dt": "10-03-2016",
      "itms": [
        {
          "ty": "S",
          "hsn_sc": "S9043",
          "ad_amt": 10,
          "irt": 3,
          "iamt": 833.33,
          "crt": 4,
          "camt": 500,
          "srt": 5,
          "samt": 900,
          "csrt": 2,
          "csamt": 500
        }
      ]
    }
  ],
  "exp": [
    {
      "ex_tp": "WPAY",
      "inv": [
        {
          "inum": "81542",
          "idt": "12-02-2016",
          "val": 995048.36,
          "sbpcode": "ASB9950",
          "sbnum": "84298",
          "sbdt": "04-10-2016",
          "prs": "Y",
          "od_num": "DR008400",
          "od_dt": "20-11-2016",
          "itms": [
            {
              "ty": "G",
              "hsn_sc": "G9207",
              "txval": 10000,
              "irt": 3,
              "iamt": 833.33,
              "crt": 4,
              "camt": 500,
              "srt": 5,
              "samt": 900,
              "csrt": 2,
              "csamt": 500
            }
          ]
        }
      ]
    }
  ],
  "expa": [
    {
      "ex_tp": "WPAY",
      "inv": [
        {
          "oinum": "81542",
          "oidt": "12-02-2016",
          "inum": "815421",
          "idt": "22-02-2016",
          "val": 995048.36,
          "sbpcode": "ASB9950",
          "sbnum": "84298",
          "sbdt": "04-10-2016",
          "prs": "Y",
          "od_num": "DR008400",
          "od_dt": "20-11-2016",
          "itms": [
            {
              "ty": "G",
              "hsn_sc": "G9207",
              "txval": 10000,
              "irt": 3,
              "iamt": 833.33,
              "crt": 4,
              "camt": 500,
              "srt": 5,
              "samt": 900,
              "csrt": 2,
              "csamt": 500
            }
          ]
        }
      ]
    }
  ],
  "nil": [
    {
      "g": [
        {
          "sply_ty": "INTRB2B",
          "expt_amt": 123.45,
          "nil_amt": 1470.85,
          "ngsup_amt": 1258.5
        },
        {
          "sply_ty": "INTRB2C",
          "expt_amt": 123.45,
          "nil_amt": 1470.85,
          "ngsup_amt": 1258.5
        },
        {
          "sply_ty": "INTRAB2B",
          "expt_amt": 123.45,
          "nil_amt": 1470.85,
          "ngsup_amt": 1258.5
        },
        {
          "sply_ty": "INTRAB2C",
          "expt_amt": 123.45,
          "nil_amt": 1470.85,
          "ngsup_amt": 1258.5
        }
      ],
      "s": [
        {
          "sply_ty": "INTRB2B",
          "expt_amt": 123.45,
          "nil_amt": 1470.85,
          "ngsup_amt": 1258.5
        },
        {
          "sply_ty": "INTRB2C",
          "expt_amt": 123.45,
          "nil_amt": 1470.85,
          "ngsup_amt": 1258.5
        },
        {
          "sply_ty": "INTRAB2B",
          "expt_amt": 123.45,
          "nil_amt": 1470.85,
          "ngsup_amt": 1258.5
        },
        {
          "sply_ty": "INTRAB2C",
          "expt_amt": 123.45,
          "nil_amt": 1470.85,
          "ngsup_amt": 1258.5
        }
      ]
    }
  ],
  "hsn": [
    {
      "data": [
        {
          "num": 1,
          "ty": "G",
          "hsn_sc": "1009",
          "txval": 10.23,
          "irt": 12.52,
          "iamt": 14.52,
          "crt": 78.52,
          "camt": 78.52,
          "srt": 12.34,
          "samt": 12.9,
          "csrt": 2,
          "csamt": 500,
          "desc": "Goods Description",
          "uqc": "1",
          "qty": 2.05,
          "sply_ty": "INTRB2B"
        }
      ]
    }
  ],
  "txpd": [
    {
      "typ": "B2B",
      "cpty": "27ABCDE7588L1ZJ",
      "inum": "533515",
      "idt": "20-10-2016",
      "doc_num": "533515",
      "doc_dt": "23-09-2016",
      "irt": 3,
      "iamt": 833.33,
      "crt": 4,
      "camt": 500,
      "srt": 5,
      "samt": 900,
      "csrt": 2,
      "csamt": 500
    }
  ]
}
```

> The above command returns JSON structured like this:

```json
{
  "ref_id": "LAPN24235325555",
  "txn_id": "TXND24235325555"
}
```

### HTTP Request

`POST https://unifiedgst.com/taxpayerapi/v0.2/returns/gstr1`

## GSTR2

This API is used to save entire GSTR2 invoices.

```JSON
{
  "gstin": "07CQZCD1111I4Z7",
  "fp": "082016",
  "crclm_17_3": "N",
  "b2b": [
    {
      "ctin": "01AABCE2207R1Z5",
      "inv": [
        {
          "inum": "S008400",
          "idt": "24-11-2016",
          "val": 729248.16,
          "pos": "06",
          "rchrg": "N",
          "itms": [
            {
              "num": 1,
              "itm_det": {
                "ty": "S",
                "hsn_sc": "G1221",
                "txval": 6210.99,
                "irt": 0,
                "iamt": 0,
                "crt": 37.4,
                "camt": 614.44,
                "srt": 33.41,
                "samt": 5.68,
                "csrt": 10,
                "csamt": 621.09,
                "elg": "ip"
              },
              "itc": {
                "tx_i": 147.2,
                "tx_s": 159.3,
                "tx_c": 159.3,
                "tx_cs": 0,
                "tc_c": 0,
                "tc_i": 7896.3,
                "tc_s": 4563.2,
                "tc_cs": 0
              }
            },
            {
              "num": 2,
              "itm_det": {
                "ty": "S",
                "hsn_sc": "G1231",
                "txval": 1000.05,
                "irt": 0,
                "iamt": 0,
                "crt": 37.45,
                "camt": 887.44,
                "srt": 33.41,
                "samt": 5.68,
                "csrt": 5.12,
                "csamt": 50.12,
                "elg": "ip"
              },
              "itc": {
                "tx_i": 147.2,
                "tx_s": 159.3,
                "tx_c": 159.3,
                "tx_cs": 0,
                "tc_c": 0,
                "tc_i": 7896.3,
                "tc_s": 4563.2,
                "tc_cs": 0
              }
            }
          ]
        }
      ]
    }
  ],
  "b2bur": [
    {
      "inv": [
        {
          "cname": "Kamath Food Ltd.",
          "inum": "S008400",
          "idt": "24-11-2016",
          "val": 729248.16,
          "pos": "06",
          "rchrg": "N",
          "itms": [
            {
              "num": 1,
              "itm_det": {
                "ty": "S",
                "hsn_sc": "G1221",
                "txval": 6210.99,
                "irt": 0,
                "iamt": 0,
                "crt": 37.4,
                "camt": 614.44,
                "srt": 33.41,
                "samt": 5.68,
                "csrt": 10,
                "csamt": 621.09,
                "elg": "ip"
              },
              "itc": {
                "tx_i": 147.2,
                "tx_s": 159.3,
                "tx_c": 159.3,
                "tx_cs": 0,
                "tc_c": 0,
                "tc_i": 7896.3,
                "tc_s": 4563.2,
                "tc_cs": 0
              }
            },
            {
              "num": 2,
              "itm_det": {
                "ty": "S",
                "hsn_sc": "G1231",
                "txval": 1000.05,
                "irt": 0,
                "iamt": 0,
                "crt": 37.45,
                "camt": 887.44,
                "srt": 33.41,
                "samt": 5.68,
                "csrt": 5.12,
                "csamt": 50.12,
                "elg": "ip"
              },
              "itc": {
                "tx_i": 147.2,
                "tx_s": 159.3,
                "tx_c": 159.3,
                "tx_cs": 0,
                "tc_c": 0,
                "tc_i": 7896.3,
                "tc_s": 4563.2,
                "tc_cs": 0
              }
            }
          ]
        }
      ]
    }
  ],
  "b2ba": [
    {
      "ctin": "01AABCE2207R1Z5",
      "inv": [
        {
          "inum": "S008400",
          "idt": "24-11-2016",
          "oinum": "S008400",
          "oidt": "24-11-2016",
          "val": 729248.16,
          "pos": "06",
          "rchrg": "N",
          "itms": [
            {
              "num": 1,
              "itm_det": {
                "ty": "S",
                "hsn_sc": "G1221",
                "txval": 6210.99,
                "irt": 0,
                "iamt": 0,
                "crt": 37.4,
                "camt": 614.44,
                "srt": 33.41,
                "samt": 5.68,
                "csrt": 10,
                "csamt": 621.09,
                "elg": "ip"
              },
              "itc": {
                "tx_i": 147.2,
                "tx_s": 159.3,
                "tx_c": 159.3,
                "tx_cs": 0,
                "tc_c": 0,
                "tc_i": 7896.3,
                "tc_s": 4563.2,
                "tc_cs": 0
              }
            },
            {
              "num": 2,
              "itm_det": {
                "ty": "S",
                "hsn_sc": "G1231",
                "txval": 1000.05,
                "irt": 0,
                "iamt": 0,
                "crt": 37.45,
                "camt": 887.44,
                "srt": 33.41,
                "samt": 5.68,
                "csrt": 5.12,
                "csamt": 50.12,
                "elg": "ip"
              },
              "itc": {
                "tx_i": 147.2,
                "tx_s": 159.3,
                "tx_c": 159.3,
                "tx_cs": 0,
                "tc_c": 0,
                "tc_i": 7896.3,
                "tc_s": 4563.2,
                "tc_cs": 0
              }
            }
          ]
        }
      ]
    }
  ],
  "b2bura": [
    {
      "inv": [
        {
          "cname": "Kamath Food Ltd.",
          "inum": "S008400",
          "idt": "24-11-2016",
          "oinum": "S008400",
          "oidt": "24-11-2016",
          "val": 729248.16,
          "pos": "06",
          "rchrg": "N",
          "itms": [
            {
              "num": 1,
              "itm_det": {
                "ty": "S",
                "hsn_sc": "G1221",
                "txval": 6210.99,
                "irt": 0,
                "iamt": 0,
                "crt": 37.4,
                "camt": 614.44,
                "srt": 33.41,
                "samt": 5.68,
                "csrt": 10,
                "csamt": 621.09,
                "elg": "ip"
              },
              "itc": {
                "tx_i": 147.2,
                "tx_s": 159.3,
                "tx_c": 159.3,
                "tx_cs": 0,
                "tc_c": 0,
                "tc_i": 7896.3,
                "tc_s": 4563.2,
                "tc_cs": 0
              }
            },
            {
              "num": 2,
              "itm_det": {
                "ty": "S",
                "hsn_sc": "G1231",
                "txval": 1000.05,
                "irt": 0,
                "iamt": 0,
                "crt": 37.45,
                "camt": 887.44,
                "srt": 33.41,
                "samt": 5.68,
                "csrt": 5.12,
                "csamt": 50.12,
                "elg": "ip"
              },
              "itc": {
                "tx_i": 147.2,
                "tx_s": 159.3,
                "tx_c": 159.3,
                "tx_cs": 0,
                "tc_c": 0,
                "tc_i": 7896.3,
                "tc_s": 4563.2,
                "tc_cs": 0
              }
            }
          ]
        }
      ]
    }
  ],
  "cdn": [
    {
      "ctin": "01AAAAP1208Q1ZS",
      "nt": [
        {
          "ntty": "C",
          "nt_num": "533515",
          "nt_dt": "23-09-2016",
          "rsn": "Not mentioned",
          "inum": "915914",
          "idt": "23-09-2016",
          "rchrg": "N",
          "val": 5225.28,
          "irt": 48.76,
          "iamt": 845.22,
          "crt": 95.79,
          "camt": 37661.29,
          "srt": 6.45,
          "samt": 42.13,
          "csrt": 10,
          "csamt": 789.52,
          "elg": "ip",
          "itc": {
            "tx_i": 147.2,
            "tx_s": 159.3,
            "tx_c": 159.3,
            "tx_cs": 0,
            "tc_c": 0,
            "tc_i": 7896.3,
            "tc_s": 4563.2,
            "tc_cs": 0
          }
        }
      ]
    }
  ],
  "cdna": [
    {
      "ctin": "01AAAAP1208Q1ZS",
      "nt": [
        {
          "ntty": "C",
          "nt_num": "533515",
          "nt_dt": "23-09-2016",
          "ont_num": "533515",
          "ont_dt": "23-09-2016",
          "rsn": "Not mentioned",
          "inum": "915914",
          "idt": "23-09-2016",
          "rchrg": "N",
          "val": 5225.28,
          "irt": 48.76,
          "iamt": 845.22,
          "crt": 95.79,
          "camt": 37661.29,
          "srt": 6.45,
          "samt": 42.13,
          "csrt": 10,
          "csamt": 789.52,
          "elg": "ip",
          "itc": {
            "tx_i": 147.2,
            "tx_s": 159.3,
            "tx_c": 159.3,
            "tx_cs": 0,
            "tc_c": 0,
            "tc_i": 7896.3,
            "tc_s": 4563.2,
            "tc_cs": 0
          }
        }
      ]
    }
  ],
  "hsnsum": [
    {
      "num": 1,
      "ty": "S",
      "hsn_sc": "S4056",
      "desc": "OPIWifhkbZzlcji",
      "uqc": "Kg",
      "qty": 80,
      "sup_ty": "INTRAB2B",
      "txval": 8451.65,
      "irt": 0,
      "iamt": 0,
      "crt": 16.09,
      "camt": 0.83,
      "srt": 75.14,
      "samt": 6736920.69,
      "csrt": 0,
      "csamt": 0
    }
  ],
  "imp_g": [
    {
      "boe_num": "25662",
      "boe_dt": "23-09-2016",
      "boe_val": 338203.29,
      "port_code": "2A",
      "itms": [
        {
          "num": 1,
          "hsn_sc": "H761",
          "txval": 582.88,
          "irt": 10.5,
          "iamt": 159.3,
          "csrt": 10.5,
          "csamt": 159.3,
          "elg": "ip",
          "tx_i": 123.02,
          "tc_i": 50.3,
          "tx_cs": 0,
          "tc_cs": 0
        },
        {
          "num": 2,
          "hsn_sc": "H761",
          "txval": 582.88,
          "irt": 10.5,
          "iamt": 159.3,
          "csrt": 10.5,
          "csamt": 159.3,
          "elg": "ip",
          "tx_i": 123.02,
          "tc_i": 50.3,
          "tx_cs": 0,
          "tc_cs": 0
        }
      ]
    }
  ],
  "imp_ga": [
    {
      "boe_num": "25662",
      "boe_dt": "23-09-2016",
      "boe_val": 338203.29,
      "port_code": "2A",
      "oboe_num": "85620",
      "oboe_dt": "22-03-2016",
      "itms": [
        {
          "num": 1,
          "hsn_sc": "H761",
          "txval": 582.88,
          "irt": 10.5,
          "iamt": 159.3,
          "csrt": 10.5,
          "csamt": 159.3,
          "elg": "ip",
          "tx_i": 123.02,
          "tc_i": 50.3,
          "tx_cs": 0,
          "tc_cs": 0
        },
        {
          "num": 2,
          "hsn_sc": "H761",
          "txval": 582.88,
          "irt": 10.5,
          "iamt": 159.3,
          "csrt": 10.5,
          "csamt": 159.3,
          "elg": "ip",
          "tx_i": 123.02,
          "tc_i": 50.3,
          "tx_cs": 0,
          "tc_cs": 0
        }
      ]
    }
  ],
  "imp_s": [
    {
      "i_num": "85619",
      "i_dt": "22-03-2016",
      "i_val": 962559.86,
      "itms": [
        {
          "num": 1,
          "sac": "S761",
          "txval": 582.88,
          "elg": "ip",
          "irt": 10.5,
          "iamt": 123.02,
          "csrt": 0,
          "csamt": 0,
          "tx_i": 500,
          "tc_i": 150.2,
          "tx_cs": 0,
          "tc_cs": 0
        },
        {
          "num": 2,
          "sac": "S762",
          "txval": 582.88,
          "elg": "ip",
          "irt": 10.5,
          "iamt": 123.02,
          "csrt": 0,
          "csamt": 0,
          "tx_i": 500,
          "tc_i": 150.2,
          "tx_cs": 0,
          "tc_cs": 0
        }
      ]
    }
  ],
  "imp_sa": [
    {
      "i_num": "85619",
      "i_dt": "22-03-2016",
      "oi_num": "75615",
      "oi_dt": "22-02-2016",
      "i_val": 962559.86,
      "itms": [
        {
          "num": 1,
          "sac": "S761",
          "txval": 582.88,
          "elg": "ip",
          "irt": 10.5,
          "iamt": 123.02,
          "csrt": 0,
          "csamt": 0,
          "tx_i": 500,
          "tc_i": 150.2,
          "tx_cs": 0,
          "tc_cs": 0
        },
        {
          "num": 2,
          "sac": "S762",
          "txval": 582.88,
          "elg": "ip",
          "irt": 10.5,
          "iamt": 123.02,
          "csrt": 0,
          "csamt": 0,
          "tx_i": 500,
          "tc_i": 150.2,
          "tx_cs": 0,
          "tc_cs": 0
        }
      ]
    }
  ],
  "itc_rcd": [
    {
      "typ": "B2B",
      "stin": "06ADECO9084R5Z4",
      "inv_doc_num": "85619",
      "inv_doc_dt": "22-03-2016",
      "o_ig": 200,
      "n_ig": 300,
      "o_cg": 200,
      "n_cg": 300,
      "o_sg": 200,
      "n_sg": 300,
      "o_cs": 200,
      "n_cs": 300
    }
  ],
  "nil_supplies": [
    {
      "sply_ty": "INTER",
      "nil_data": [
        {
          "ty": "G",
          "hsn_sc": "H761",
          "cpddr": 1000,
          "uredr": 1000,
          "exptdsply": 5394970.87,
          "ngsply": 992.93,
          "nilsply": 0
        }
      ]
    },
    {
      "sply_ty": "INTRA",
      "nil_data": [
        {
          "ty": "G",
          "hsn_sc": "H761",
          "cpddr": 1000,
          "uredr": 1000,
          "exptdsply": 5394970.87,
          "ngsply": 992.93,
          "nilsply": 0
        }
      ]
    }
  ],
  "txi": [
    {
      "cpty": "30ABCDE3304F2Z6",
      "reg_type": "REGD",
      "state_cd": "12",
      "dnum": "A100052",
      "dt": "21-03-2016",
      "itms": [
        {
          "ty": "S",
          "hsn_sc": "S8774",
          "txval": 2354.92,
          "irt": 0,
          "iamt": 0,
          "crt": 62.3,
          "camt": 863.12,
          "srt": 24.45,
          "samt": 8.37361437,
          "csrt": 24.45,
          "csamt": 8.37361437
        }
      ]
    }
  ],
  "atxi": [
    {
      "cpty": "30ABCDE3304F2Z6",
      "reg_type": "REGD",
      "state_cd": "12",
      "dnum": "A100052",
      "dt": "21-03-2016",
      "oreg_type": "REGD",
      "ocpty": "ABC125245123412",
      "odnum": "A100052",
      "otdt": "20-05-2016",
      "itms": [
        {
          "ty": "S",
          "hsn_sc": "S8774",
          "txval": 2354.92,
          "irt": 0,
          "iamt": 0,
          "crt": 62.3,
          "camt": 863.12,
          "srt": 24.45,
          "samt": 8.37361437,
          "csrt": 24.45,
          "csamt": 8.37361437
        }
      ]
    }
  ],
  "txpd": [
    {
      "i_num": "88017",
      "i_dt": "12-05-2016",
      "doc": [
        {
          "doc_num": "100012",
          "irt": 0,
          "iamt": 0,
          "crt": 58.07,
          "camt": 2857274.18,
          "srt": 22.27,
          "samt": 49848872.07,
          "csrt": 0,
          "csamt": 0
        }
      ]
    }
  ],
  "itc_rvsl": [
    {
      "stin": "06ADECO9084R5Z4",
      "typ": "B2B",
      "inv_doc_num": "S008400",
      "inv_doc_dt": "24-11-2016",
      "des": "description of XYA",
      "iamt": 789.32,
      "camt": 456.1,
      "samt": 741.02,
      "csamt": 123.32
    }
  ],
  "itc_rvsla": [
    {
      "stin": "06ADECO9084R5Z4",
      "typ": "B2B",
      "inv_doc_num": "S008400",
      "inv_doc_dt": "24-11-2016",
      "des": "description of XYA",
      "iamt": 789.32,
      "camt": 456.1,
      "samt": 741.02,
      "csamt": 123.32
    }
  ],
  "inv_pd": [
    {
      "stin": "06ADECO9084R5Z4",
      "inum": "S008400",
      "idt": "24-11-2016",
      "taxval": 1046.8,
      "iamt": 789.32,
      "camt": 456.1,
      "samt": 741.02,
      "csamt": 123.32
    }
  ],
  "inv_upd": [
    {
      "stin": "06ADECO9084R5Z4",
      "inum": "S008400",
      "idt": "24-11-2016",
      "taxval": 1046.8,
      "iamt": 789.32,
      "camt": 456.1,
      "samt": 741.02,
      "csamt": 123.32
    }
  ]
}
```

> The above command returns JSON structured like this:

```json
{
  "ref_id": "LAPN24235325555",
  "txn_id": "TXND24235325555"
}
```

### HTTP Request

`POST https://unifiedgst.com/taxpayerapi/v0.2/authenticate/returns/gstr2`

## GSTR3

API call for saving all GSTR3 details.

```JSON
{
  "gstin": "05ABVPJ8672P1ZK",
  "ret_period": "102016",
  "refclm": {
    "igrfclm": {
      "tax": 10,
      "int": 20,
      "pen": 30,
      "fee": 40,
      "oth": 50
    },
    "cgrfclm": {
      "tax": 20,
      "int": 30,
      "pen": 40,
      "fee": 50,
      "oth": 60
    },
    "sgrfclm": {
      "tax": 30,
      "int": 40,
      "pen": 50,
      "fee": 60,
      "oth": 70
    },
    "csrfclm": {
      "tax": 40,
      "int": 50,
      "pen": 60,
      "fee": 70,
      "oth": 80
    },
    "bankacc": 123456
  }
}
```

> The above command returns JSON structured like this:

```json
{
  "status_cd": "1",
  "message": "SUCCESS"
}
```

### HTTP Request

`POST https://unifiedgst.com/taxpayerapi/v0.2/authenticate/returns/gstr3`

