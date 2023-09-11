## Bicep Test Modules - Folder structure

The folder structure must resemble the following for any new modules created:

```
└── bicep/
    └── modules/
        ├── storageAccount/
        │   └── .tests/
        │       └── storageAccount.tests.bicep
        ├── storage.bicep
        └── metadata.json
```

The tests file must be formatted as above, with the declared required-params specified for test deployments, for example:

```
// Test with only required parameters
module test_required_params '../storageAccount.bicep' = {
  name: 'test_required_params'
  params: {
    location: 'uksouth'
    tags: {
      Demo: 'Rios Engineer Blog'
    }
    storageName: 'riosengineerst001'
    storageSkuName: 'Standard_GRS'
    storagePleBlobName: 'someBlob'
    storagePleFileName: 'someFileshare'
    subnetId: 'test'
    virtualNetworkId: 'test'
  }
}
```

The metadata.json is to contain some basic summary and description of the module, for example: 
```
    {
        "itemDisplayName": "Storage Account Module.",
        "description": "Storage Account Bicep Module",
        "summary": "Storage Account Bicep standard for deployments"
    }
```