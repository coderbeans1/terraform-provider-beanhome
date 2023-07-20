---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "coolbeans_vsp_storage_ports Data Source - terraform-provider-coolbeans"
subcategory: ""
description: |-
  
---

# coolbeans_vsp_storage_ports (Data Source)





<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `serial` (Number)

### Optional

- `port_id` (String)
- `total_port_count` (Number)

### Read-Only

- `id` (String) The ID of this resource.
- `info` (List of Object) (see [below for nested schema](#nestedatt--info))

<a id="nestedatt--info"></a>
### Nested Schema for `info`

Read-Only:

- `fabric_mode` (Boolean)
- `loop_id` (String)
- `lun_security_setting` (Boolean)
- `port_attributes` (List of String)
- `port_connection` (String)
- `port_id` (String)
- `port_speed` (String)
- `port_type` (String)
- `wwn` (String)

