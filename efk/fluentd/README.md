# Issue Notes

## ES

- Startup failed due to default CentOS setting when running in VM
  - sysctl -w vm.max_map_count=262144
