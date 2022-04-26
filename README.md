# OCDS award buyer extension

When modelling framework agreements with direct call offs, the information about the framework set up should go in the award block. The OCDS award buyer extension adds a buyer field to the award block to distinguish who buys what under the framework agreement.

## Example

A tender is issued for a framework agreement which has two buyers. The successful supplier is awarded work under the framework agreement by both of the buyers.

```json
	{
		"parties": [
	   	{
				"name": "The Borough Council of Borsetdale",
				"id": "1",
				"identifier": {
					"scheme": "GB-LAE",
          "id": "CLD"
          },
        "roles": [
         	"buyer"
         	]
        },
      {
        "name": "NHS Borsetdale Clinical Commissioning Group",
        "id": "2",
        "identifier": {
          "scheme": "GB-NHS",
          "id": "02T"
          },
        "roles": [
        	"buyer"
          ]                    
        },
      {
        "name": "Equal Care Co-op",
        "id": "3",
        "identifier": {
          "scheme": "GB-MPR",
          "id": 4453
          },
        "roles": [
          "supplier"
          ]
        },
      ],
    "tender": {
      "id": "ocds-h6vhtk-02c615",
      "title": "The Provision of  All Age Domiciliary Care Services - Approved Provider List",
      "status": "active",
      "classification": {
      	"scheme": "CPV",
        "id": "85000000",
        "description": "Health and social work services"
      },
      "mainProcurementCategory": "services",
      "description": "The Borough Council of Borsetdale ("the Council") and NHS Borsetdale Clinical Commissioning Group ("the CCG") invites tenders from tenderers who wish to be considered for appointment to the All Age Domiciliary Care Services - Approved Provider List.
      "value": {
        "amount": 9600000,
        "currency": "GBP"
      },
      "lotDetails": {
        "maximumLotsBidPerSupplier": Infinity,
        "maximumLotsAwardedPerSupplier": 2
      },
      "lots": [
        {
        	"id": "1",
          "title": "Lot 1 - Council Contract",
          "description": "The Borough Council of Borsetdale Approved Provider List.",
          "awardCriteria": {
            "criteria": [
              {
                "name": "Quality",
                "type": "quality",
                "description": "100%"
              },
              {
                "name": "Fixed Price",
                "type": "cost",
                "description": "0%"
              }
            ]
          },
          "value": {
            "amount": 3600000,
            "currency": "GBP"
          },
          "contractPeriod": {
            "durationInDays": 2160
          },
          "hasRenewal": true,
          "renewal": {
            "description": "48 month contract with the option to extend by a period or periods of up to 24 months"
            },
          "submissionTerms": {
            "variantPolicy": "notAllowed"
            },
          "hasOptions": false,
          "status": "active"
        },
        {
          "id": "2",
          "title": "Lot 2 - CCG Contract",
          "description": "The NHS Borsetdale Clinical Commissioning Group Approved Provider List..",
          "awardCriteria": {
            "criteria": [
              {
                "name": "Quality",
                "type": "quality",
                "description": "100%"
              },
              {
                "name": "Fixed Price",
                "type": "cost",
                "description": "0%"
              }
            ]
          },
          "value": {
            "amount": 6000000,
            "currency": "GBP"
          },
          "contractPeriod": {
          	"durationInDays": 2160
            },
          "hasRenewal": true,
          	"renewal": {
              "description": "48 month contract with the option to extend by a period or periods of up to 24 months"
              },
          "submissionTerms": {
          	"variantPolicy": "notAllowed"
            },
          "hasOptions": false,
          "status": "active"
        }
      ],
		"items": [
      {
       "id": "1",
       "additionalClassifications": [
         {
         "scheme": "CPV",
         "id": "85000000",
         "description": "Health and social work services"
	       }
       ],
       "deliveryAddresses": [
         {
         "region": "UKE44"
         }
       ],
       "relatedLot": "1"
       },
       {
        "id": "2",
        "additionalClassifications": [
	        {
          "scheme": "CPV",
          "id": "85000000",
          "description": "Health and social work services"
          }
        ],
        "deliveryAddresses": [
	        {
          "region": "UKE44"
	        }
        ],
        "relatedLot": "2"
        }
      ],
    "awards": [
      {
	      "id": "GB-LAE-CLD-GB-MPR-4453-001",
        "buyer": {
          "name": "The Borough Council of Borsetdale",
          "id": "1"
          },
        "relatedLots": [
 	       "1"
        ],
        "suppliers": [
          {
            "name": "Equal Care Co-op",
            "id": "GB-MPR-4453"
          }
        ]
      },
      {
        "id": "GB-NHS-02T-GB-MPR-4453-001",
 	     "buyer": {
         "name": "NHS Borsetdale Clinical Commissioning Group",
         "id": 2
         },
 	      "relatedLots": [
          "2"
 	       ],
        "suppliers": [
 	       {
          "name": "Equal Care Co-op",
          "id": "GB-MPR-4453"
         }
       ]
     }
   ],
 }
```
