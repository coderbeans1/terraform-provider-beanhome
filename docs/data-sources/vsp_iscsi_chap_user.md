---
# generated by https://github.com/fbreckle/terraform-plugin-docs
page_title: "hitachi_vsp_iscsi_chap_user Data Source - terraform-provider-hitachi"
subcategory: "VSP Storage ISCSI Targets"
description: |-
  Using the specified port and iSCSI target, the following request gets the CHAP user information that is specified for the iSCSI target.
---

# hitachi_vsp_iscsi_chap_user (Data Source)

Using the specified port and iSCSI target, the following request gets the CHAP user information that is specified for the iSCSI target.

## Example Usage

```terraform
data "hitachi_vsp_iscsi_chap_user" "my_iscsi_initiator_chap_user" {
  serial              = 30078
  port_id             = "CL4-C"
  iscsi_target_number = 1
  chap_user_type      = "initiator" # valid input value : "initiator", "target"
  chap_user_name      = "dan"

}

#data "hitachi_vsp_iscsi_chap_user" "my_iscsi_target_chap_user" {
#   serial   = 30078
#   port_id   = "CL4-C"
#   iscsi_target_number   = 1
#   chap_user_type = "target" # valid input value : "initiator", "target"
#   chap_user_name = "rahul"

#}


output "my_iscsi_initiator_chap_user_output" {
  value = data.hitachi_vsp_iscsi_chap_user.my_iscsi_initiator_chap_user
}


#output "my_iscsi_target_chap_user_output" {
#  value = data.hitachi_vsp_iscsi_chap_user.my_iscsi_target_chap_user
#}
data "hitachi_vsp_iscsi_chap_users" "my_iscsi_chap_users" {
  serial              = 30078
  port_id             = "CL4-C"
  iscsi_target_number = 1

}


output "my_iscsi_chap_users_output" {
  value = data.hitachi_vsp_iscsi_chap_users.my_iscsi_chap_users
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `chap_user_name` (String) The CHAP user name.
- `chap_user_type` (String) Type of the CHAP user name
		o target : The CHAP user name of the iSCSI target side
		o initiator : The CHAP user name of the host bus adapter (iSCSI initiator) side
- `iscsi_target_number` (Number) Target ID of the iSCSI target.
- `port_id` (String) Port number
- `serial` (Number) The serial number of the storage

### Read-Only

- `id` (String) The ID of this resource.
- `info` (List of Object) This is output schema (see [below for nested schema](#nestedatt--info))

<a id="nestedatt--info"></a>
### Nested Schema for `info`

Read-Only:

- `chap_user_id` (String)
- `chap_user_name` (String)
- `chap_user_type` (String)
- `iscsi_target_number` (Number)
- `port_id` (String)
- `storage_serial_number` (Number)

