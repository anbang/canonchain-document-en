# Command Line Interface

```
    $ canonchain --help
    NAME:
       canonchain - the canonchain command line interface

    USAGE:
       canonchain command [command options] [arguments...]
       
    VERSION:
       1.0-stable

    COMMANDS:
      --account_create             Create new account
      --account_remove             Remove account
        arguments：
          --account                  Account
      --account_import             Imports account from json file
        arguments：
          --file                     Account file
      --account_list               List all accounts
      --daemon                     Start node daemon 
      --help                       Print parameter options
      --version                    Print version

    NODE OPTIONS:
      --network                    Network id（Default：1 - mainnet）
      --data_path                  Use the supplied path as the data directory
      --io_threads                 Number of io threads       
      --bg_threads                 Number of background threads
      --sync_threads               Number of syncing threads

    RPC OPTIONS:
      --rpc                        Enable the HTTP-RPC server
      --rpc_addr                   HTTP-RPC server listening interface (default: 127.0.0.1)
      --rpc_port                   HTTP-RPC server listening port (default: 8765)
      --rpc_control                Enable the HTTP-RPC write permission

    WS OPTIONS:
      --ws                         Enable the WS-RPC server  
      --ws_addr                    WS-RPC server listening interface (default: 127.0.0.1)
      --ws_port                    WS-RPC server listening port (default: 8764)
      --ws_control                 Enable the WS-RPC write permission

    LOG OPTIONS:
      --console                    Enable output log to console
      --max_size                   The maximum total size of rotated files 
      --rotation_size              The size of the file at which rotation should occur
      --flush                      Automatically flush the file after each written record    
      --verbosity                  Logging verbosity: none,error,warning,info,debug,trace (default: info)
      --vmodule                    Per-module verbosity: comma-separated list of <module>=<level>（current module list: node,p2p,rpc,db,sync)  
           
    P2P OPTIONS:
      --addr                       Network listening interface (default: 127.0.0.1)
      --port                       Network listening port (default: 30606)
      --max_peers                  Maximum number of network peers (network disabled if set to 0) (default: 25)
      --bootstrap_nodes            Comma separated enode URLs for P2P discovery bootstrap
      --exemption_nodes            Comma separated enode URLs for P2P exemption node
      --nat                        NAT penetration

    WITNESS OPTIONS:               
      --witness                    Enable witness mode      
      --witness_account            Witness account address or account json file
      --password                   Witness account password  
      --last_block                 The last block hash for the witness to sync. The witness starts to work if and only if the node receives the last block. 
    MISC OPTIONS:               
      --config                     Config file       
```
### Config file
config.json - in the node data path. An examples as the following:
```
    {
        "version": 3,
        "network": 4,
        "node": {
            "io_threads": 8,
            "bg_threads": 4,
            "sync_threads": 4,
            "work_threads": 2
        },
        "rpc": {
            "rpc": "false",
            "rpc_addr": "127.0.0.1",
            "rpc_port": 8765,
            "rpc_control": "false"
        },
        "ws": {
            "ws": "false",
            "ws_addr": "127.0.0.1",
            "ws_port": 8764,
            "ws_control": "false"
        },
        "log": {
            "console": "false",
            "max_size": 16777216,
            "rotation_size": 4194304,
            "flush": "true",
            "verbosity": "info",
            "vmodule": ""
        },
        "p2p": {
            "host": "",
            "port": 30606,
            "max_peers": 25,
            "bootstrap_nodes": [
                "czrnode://927A2362C7CB382E8574D2BD94EC5475D92170B8EBA91D019175185B4FFE4D52@47.34.12.16:30606",
                "czrnode://01CE1577F493C721ED0200A53A3E90C238F897DF0A845DA195C512F37D1D5229@78.65.15.17:30614",
            ],
            "exemption_nodes": [
                "czrnode://01CE1577F493C721ED0200A53A3E90C238F897DF0A845DA195C512F37D1D5229@78.65.15.17:30614"
            ],
            "nat": "true"
        },
        "witness": {
            "witness": "false",
            "witness_account": "",
            "password": "",
            "last_block": ""
        }
    }
```