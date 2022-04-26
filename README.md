# Usage
```
Usage of ./nomad-exporter:
  -nomad.server string
    	HTTP API address of a Nomad server or agent. (default "http://localhost:4646")
  -nomad.timeout string
    	HTTP timeout to contact Nomad agent. (default "30")
  -tls.ca-file string
    	ca-file path to a PEM-encoded CA cert file to use to verify the connection to nomad server
  -tls.ca-path string
    	ca-path is the path to a directory of PEM-encoded CA cert files to verify the connection to nomad server
  -tls.cert-file string
    	cert-file is the path to the client certificate for Nomad communication
  -tls.insecure
    	insecure enables or disables SSL verification
  -tls.key-file string
    	key-file is the path to the key for cert-file
  -tls.tls-server-name string
    	tls-server-name sets the SNI for Nomad ssl connection
  -version
    	Print version information.
  -web.listen-address string
    	Address to listen on for web interface and telemetry. (default ":9172")
  -web.telemetry-path string
    	Path under which to expose metrics. (default "/metrics")
```

## Exported Metrics

| Metric | Meaning | Labels |
| ------ | ------- | ------ |
| nomad_up | Was the last query of Nomad successful | |
| nomad_raft_peers | How many peers (servers) are in the Raft cluster | |
| nomad_serf_lan_members | How many members are in the cluster | |
| nomad_jobs | How many jobs are in the cluster | |
| nomad_allocations | How many allocations are in the cluster | |
| nomad_allocation_cpu | How much CPU allocation is consuming | job, group, alloc, alloc_id, region, datacenter, node |
| nomad_allocation_cpu_throttle | How much allocation CPU is throttled | job, group, alloc, alloc_id, region, datacenter, node|
| nomad_allocation_memory | How much memory allocation is consuming | job, group, alloc, alloc_id, region, datacenter, node |
| nomad_allocation_memory_limit | Allocation memory limit | job, group, alloc, alloc_id, region, datacenter, node |
| nomad_task_cpu_total_ticks | Task CPU total ticks | job, group, alloc, alloc_id, task, region, datacenter, node |
| nomad_task_cpu_percent | Task CPU usage, percent | job, group, alloc, alloc_id, task, region, datacenter, node |
| nomad_task_memory_limit | Task memory limit, Megabytes | job, group, alloc, alloc_id, task, region, datacenter, node |
| nomad_deployments | All current non successful deployments | job, deployment_id, status |
| nomad_task_memory_rss_bytes | Task memory RSS usage, bytes | job, group, alloc, alloc_id, task, region, datacenter, node |
| nomad_node_resource_memory_megabytes | Amount of allocatable memory the node has in MB | node, datacenter |
| nomad_node_allocated_memory_megabytes | Amount of  memory allocated to tasks on the node in MB | node, datacenter |
| nomad_node_used_memory_megabytes | Amount of memory used on the node in MB | node, datacenter |
| nomad_node_reserved_memory_megabytes | Amount of memory reserved on the node in MB | node, datacenter |
| nomad_node_resource_cpu_megahertz | Amount of allocatable CPU the node has in MHz | node, datacenter |
| nomad_node_allocated_cpu_megahertz | Amount of allocated CPU the node has | node, datacenter | 
| nomad_node_used_cpu_megahertz | Amount of CPU used on the node | node, datacenter |

