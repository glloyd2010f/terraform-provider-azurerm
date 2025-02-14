---
subcategory: "Storage"
layout: "azurerm"
page_title: "Azure Resource Manager: azurerm_storage_account"
description: |-
  Gets information about an existing Storage Account.

---

# Data Source: azurerm_storage_account

Use this data source to access information about an existing Storage Account.

## Example Usage

```hcl
data "azurerm_storage_account" "example" {
  name                = "packerimages"
  resource_group_name = "packer-storage"
}

output "storage_account_tier" {
  value = data.azurerm_storage_account.example.account_tier
}
```

## Argument Reference

* `name` - Specifies the name of the Storage Account
* `resource_group_name` - Specifies the name of the resource group the Storage Account is located in.

## Attributes Reference

* `id` - The ID of the Storage Account.

* `location` - The Azure location where the Storage Account exists

* `account_kind` - The Kind of account.

* `account_tier` - The Tier of this storage account.

* `account_replication_type` - The type of replication used for this storage account.

* `access_tier` - The access tier for `BlobStorage` accounts.

* `enable_https_traffic_only` - Is traffic only allowed via HTTPS? See [here](https://docs.microsoft.com/en-us/azure/storage/storage-require-secure-transfer/)
    for more information.

* `min_tls_version` - The minimum supported TLS version for this storage account.

* `allow_nested_items_to_be_public` - Can nested items in the storage account opt into allowing public access?

* `is_hns_enabled` - Is Hierarchical Namespace enabled?

* `custom_domain` - A `custom_domain` block as documented below.

* `tags` - A mapping of tags to assigned to the resource.

* `primary_location` - The primary location of the Storage Account.

* `secondary_location` - The secondary location of the Storage Account.

* `primary_blob_endpoint` - The endpoint URL for blob storage in the primary location.

* `primary_blob_host` - The hostname with port if applicable for blob storage in the primary location.

* `secondary_blob_endpoint` - The endpoint URL for blob storage in the secondary location.

* `secondary_blob_host` - The hostname with port if applicable for blob storage in the secondary location.

* `primary_queue_endpoint` - The endpoint URL for queue storage in the primary location.

* `primary_queue_host` - The hostname with port if applicable for queue storage in the primary location.

* `secondary_queue_endpoint` - The endpoint URL for queue storage in the secondary location.

* `secondary_queue_host` - The hostname with port if applicable for queue storage in the secondary location.

* `primary_table_endpoint` - The endpoint URL for table storage in the primary location.

* `primary_table_host` - The hostname with port if applicable for table storage in the primary location.

* `secondary_table_endpoint` - The endpoint URL for table storage in the secondary location.

* `secondary_table_host` - The hostname with port if applicable for table storage in the secondary location.

* `primary_file_endpoint` - The endpoint URL for file storage in the primary location.

* `primary_file_host` - The hostname with port if applicable for file storage in the primary location.

* `secondary_file_endpoint` - The endpoint URL for file storage in the secondary location.

* `secondary_file_host` - The hostname with port if applicable for file storage in the secondary location.

* `primary_dfs_endpoint` - The endpoint URL for DFS storage in the primary location.

* `primary_dfs_host` - The hostname with port if applicable for DFS storage in the primary location.

* `secondary_dfs_endpoint` - The endpoint URL for DFS storage in the secondary location.

* `secondary_dfs_host` - The hostname with port if applicable for DFS storage in the secondary location.

* `primary_web_endpoint` - The endpoint URL for web storage in the primary location.

* `primary_web_host` - The hostname with port if applicable for web storage in the primary location.

* `secondary_web_endpoint` - The endpoint URL for web storage in the secondary location.

* `secondary_web_host` - The hostname with port if applicable for web storage in the secondary location.

* `primary_access_key` - The primary access key for the Storage Account.

* `secondary_access_key` - The secondary access key for the Storage Account.

* `primary_connection_string` - The connection string associated with the primary location

* `secondary_connection_string` - The connection string associated with the secondary location

* `primary_blob_connection_string` - The connection string associated with the primary blob location

* `secondary_blob_connection_string` - The connection string associated with the secondary blob location

~> **Note:** If there's a Write Lock on the Storage Account, or the account doesn't have permission then these fields will have an empty value [due to a bug in the Azure API](https://github.com/Azure/azure-rest-api-specs/issues/6363)

* `queue_encryption_key_type` - The encryption key type of the queue.

* `table_encryption_key_type` - The encryption key type of the table.

* `infrastructure_encryption_enabled` - Is infrastructure encryption enabled? See [here](https://docs.microsoft.com/en-us/azure/storage/common/infrastructure-encryption-enable/)
    for more information.
---

* `custom_domain` supports the following:

* `name` - The Custom Domain Name used for the Storage Account.

## Timeouts

The `timeouts` block allows you to specify [timeouts](https://www.terraform.io/docs/configuration/resources.html#timeouts) for certain actions:

* `read` - (Defaults to 5 minutes) Used when retrieving the Storage Account.
