# OCDS award buyer extension

When modelling framework agreements with direct call offs, the information about the framework set up should go in the award block. The OCDS award buyer extension adds a buyer field to the award block to distinguish who buys what under the framework agreement.

## Example

A tender is issued for a framework agreement which has two buyers. The successful supplier is awarded work under the framework agreement by both of the buyers.

```json
{
  "awards": [
    {
      "id": "GB-LAE-ABC",
      "buyer": {
        "name": "Example Borough Council",
        "id": "1"
      }
    },
    {
      "id": "GB-NHS-000000",
      "buyer": {
        "name": "Example NHS Clinical Commissioning Group",
        "id": "2"
      }
    }
  ]
}
```
