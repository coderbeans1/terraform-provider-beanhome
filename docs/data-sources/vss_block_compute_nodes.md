---
# generated by https://github.com/fbreckle/terraform-plugin-docs
page_title: "hitachi_vss_block_compute_nodes Data Source - terraform-provider-hitachi"
subcategory: "VSS Block Compute Node"
description: |-
  Obtains a list of compute node information.
---

# hitachi_vss_block_compute_nodes (Data Source)

Obtains a list of compute node information.

## Example Usage

```terraform
data "hitachi_vss_block_compute_nodes" "computenodes" {
  vss_block_address = ""
  compute_node_name = "ComputeNode-RESTAPI123" // Optional
  #compute_node_name = "MongoNode1" // Optional   
}

output "nodeoutput" {
  value = data.hitachi_vss_block_compute_nodes.computenodes
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `vss_block_address` (String) The  VSS block address of the storage server

### Optional

- `compute_node_name` (String) The name of the compute node to be fetched

### Read-Only

- `id` (String) The ID of this resource.
- `info` (Block List) All the information if the selected compute node (see [below for nested schema](#nestedblock--info))

<a id="nestedblock--info"></a>
### Nested Schema for `info`

Read-Only:

- `id` (String) The id of the compute node
- `nickname` (String) The name of the compute node
- `number_of_paths` (Number) Number of ISCSI connection initiated to the compute node
- `number_of_volumes` (Number) The number of volumes attached in the compute node
- `os_type` (String) The OS type of the compute node
- `paths` (Block List) Path/ISCSI connections details for the compute node (see [below for nested schema](#nestedblock--info--paths))
- `port_details` (Block List) Port Details of the ISCSI connection (see [below for nested schema](#nestedblock--info--port_details))
- `total_capacity` (Number) The total capacity of the compute node in megabytes
- `used_capacity` (Number) The used capacity of the compute node in megabytes

<a id="nestedblock--info--paths"></a>
### Nested Schema for `info.paths`

Read-Only:

- `hba_name` (String) Name of the HBA connection
- `port_ids` (List of String) Port IDs of the ISCSI connection
- `protocol` (String) Type of Protocol of the attached connection


<a id="nestedblock--info--port_details"></a>
### Nested Schema for `info.port_details`

Read-Only:

- `iscsi_initiator` (String) Iscsi initiator name.
- `port_id` (String) Port ID of the connection
- `port_name` (String) Port name of the connection

