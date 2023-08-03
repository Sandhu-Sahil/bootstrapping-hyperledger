# prerequisites
```
vscode
golang (vscode extension)
docker
docker-compose
build-essential
nodejs
npm
go
WEFT library
```

# export 

```
export MICROFAB_CONFIG='{
    "endorsing_organizations":[
        {
            "name": "ProducersOrg"
        },
        {
            "name": "SellersOrg"
        }
    ],
    "channels":[
        {
            "name": "mango-channel",
            "endorsing_organizations":[
                "ProducersOrg",
                "SellersOrg"
            ]
        }
    ],
    "capability_level":"V2_0"
}'
```

# runnning microfab
```
sudo docker run --name microfab --rm -ti -p 8080:8080 -e MICROFAB_CONFIG="${MICROFAB_CONFIG}" ibmcom/ibp-microfab

```

# output
```
sudo docker run --name microfab --rm -ti -p 8080:8080 -e MICROFAB_CONFIG="${MICROFAB_CONFIG}" ibmcom/ibp-microfab
[sudo] password for sandhu-sahil: 
[       microfabd] 2023/08/03 15:13:15 Starting Microfab ...
[       microfabd] 2023/08/03 15:13:15 MBW
[       microfabd] 2023/08/03 15:13:15 Creating endorsing organization SellersOrg ...
[       microfabd] 2023/08/03 15:13:15 Creating endorsing organization ProducersOrg ...
[       microfabd] 2023/08/03 15:13:15 Creating ordering organization Orderer ...
[       microfabd] 2023/08/03 15:13:15 Created endorsing organization ProducersOrg
[       microfabd] 2023/08/03 15:13:15 Created endorsing organization SellersOrg
[       microfabd] 2023/08/03 15:13:15 Created ordering organization Orderer
[       microfabd] 2023/08/03 15:13:15 Waiting for CouchDB to start ...
[       microfabd] 2023/08/03 15:13:16 CouchDB has started
[       microfabd] 2023/08/03 15:13:16 Creating and starting CA for endorsing organization SellersOrg ...
[       microfabd] 2023/08/03 15:13:16 Creating and starting CA for endorsing organization ProducersOrg ...
[       microfabd] 2023/08/03 15:13:16 Creating and starting peer for endorsing organization ProducersOrg ...
[       microfabd] 2023/08/03 15:13:16 Creating and starting CouchDB proxy for endorsing organization ProducersOrg ...
[       microfabd] 2023/08/03 15:13:16 Creating and starting orderer for ordering organization Orderer ...
[       microfabd] 2023/08/03 15:13:16 Creating and starting peer for endorsing organization SellersOrg ...
[start --boot admin:adminpw --ca.certfile /opt/microfab/data/ca-producersorg/ca-cert.pem --ca.keyfile /opt/microfab/data/ca-producersorg/ca-key.pem --port 2008 --operations.listenaddress 0.0.0.0:2009 --ca.name producersorgca][       microfabd] 2023/08/03 15:13:16 Creating and starting CouchDB proxy for endorsing organization SellersOrg ...
[start --boot admin:adminpw --ca.certfile /opt/microfab/data/ca-sellersorg/ca-cert.pem --ca.keyfile /opt/microfab/data/ca-sellersorg/ca-key.pem --port 2000 --operations.listenaddress 0.0.0.0:2001 --ca.name sellersorgca][    sellersorgca] 2023/08/03 15:13:16 [INFO] Created default configuration file at /opt/microfab/data/ca-sellersorg/fabric-ca-server-config.yaml
[  producersorgca] 2023/08/03 15:13:16 [INFO] Created default configuration file at /opt/microfab/data/ca-producersorg/fabric-ca-server-config.yaml
[producersorgpeer] 2023-08-03 15:13:16.959 UTC 0001 INFO [nodeCmd] serve -> Starting peer:
[producersorgpeer]  Version: 2.4.6
[producersorgpeer]  Commit SHA: 83596078d
[producersorgpeer]  Go version: go1.18.2
[producersorgpeer]  OS/Arch: linux/amd64
[producersorgpeer]  Chaincode:
[producersorgpeer]   Base Docker Label: org.hyperledger.fabric
[producersorgpeer]   Docker Namespace: hyperledger
[producersorgpeer] 2023-08-03 15:13:16.960 UTC 0002 INFO [peer] getLocalAddress -> Auto-detected peer address: 172.17.0.2:2002
[producersorgpeer] 2023-08-03 15:13:16.960 UTC 0003 INFO [peer] getLocalAddress -> Host is 0.0.0.0 , falling back to auto-detected address: 172.17.0.2:2002
[producersorgpeer] 2023-08-03 15:13:16.966 UTC 0004 INFO [nodeCmd] initGrpcSemaphores -> concurrency limit for endorser service is 2500
[producersorgpeer] 2023-08-03 15:13:16.967 UTC 0005 INFO [nodeCmd] initGrpcSemaphores -> concurrency limit for deliver service is 2500
[producersorgpeer] 2023-08-03 15:13:16.967 UTC 0006 INFO [nodeCmd] initGrpcSemaphores -> concurrency limit for gateway service is 500
[         orderer] 2023-08-03 15:13:16.967 UTC 0001 INFO [localconfig] completeInitialization -> Kafka.Version unset, setting to 0.10.2.0
[         orderer] 2023-08-03 15:13:16.968 UTC 0002 INFO [orderer.common.server] prettyPrintStruct -> Orderer config values:
[         orderer]      General.ListenAddress = "0.0.0.0"
[         orderer]      General.ListenPort = 2006
[         orderer]      General.TLS.Enabled = false
[         orderer]      General.TLS.PrivateKey = "/opt/fabric/config/tls/server.key"
[         orderer]      General.TLS.Certificate = "/opt/fabric/config/tls/server.crt"
[         orderer]      General.TLS.RootCAs = [/opt/fabric/config/tls/ca.crt]
[         orderer]      General.TLS.ClientAuthRequired = false
[         orderer]      General.TLS.ClientRootCAs = []
[         orderer]      General.TLS.TLSHandshakeTimeShift = 0s
[         orderer]      General.Cluster.ListenAddress = ""
[         orderer]      General.Cluster.ListenPort = 0
[         orderer]      General.Cluster.ServerCertificate = ""
[         orderer]      General.Cluster.ServerPrivateKey = ""
[         orderer]      General.Cluster.ClientCertificate = ""
[         orderer]      General.Cluster.ClientPrivateKey = ""
[         orderer]      General.Cluster.RootCAs = []
[         orderer]      General.Cluster.DialTimeout = 5s
[         orderer]      General.Cluster.RPCTimeout = 7s
[         orderer]      General.Cluster.ReplicationBufferSize = 20971520
[         orderer]      General.Cluster.ReplicationPullTimeout = 5s
[         orderer]      General.Cluster.ReplicationRetryTimeout = 5s
[         orderer]      General.Cluster.ReplicationBackgroundRefreshInterval = 5m0s
[         orderer]      General.Cluster.ReplicationMaxRetries = 12
[         orderer]      General.Cluster.SendBufferSize = 10
[         orderer]      General.Cluster.CertExpirationWarningThreshold = 168h0m0s
[         orderer]      General.Cluster.TLSHandshakeTimeShift = 0s
[         orderer]      General.Keepalive.ServerMinInterval = 1m0s
[         orderer]      General.Keepalive.ServerInterval = 2h0m0s
[         orderer]      General.Keepalive.ServerTimeout = 20s
[         orderer]      General.ConnectionTimeout = 0s
[         orderer]      General.GenesisMethod = ""
[         orderer]      General.GenesisFile = ""
[         orderer]      General.BootstrapMethod = "file"
[         orderer]      General.BootstrapFile = "/opt/microfab/data/orderer/config/genesisblock"
[         orderer]      General.Profile.Enabled = false
[         orderer]      General.Profile.Address = "0.0.0.0:6060"
[         orderer]      General.LocalMSPDir = "/opt/microfab/data/orderer/msp"
[         orderer]      General.LocalMSPID = "OrdererMSP"
[         orderer]      General.BCCSP.Default = "SW"
[         orderer]      General.BCCSP.SW.Security = 256
[         orderer]      General.BCCSP.SW.Hash = "SHA2"
[         orderer]      General.BCCSP.SW.FileKeystore.KeyStorePath = ""
[         orderer]      General.Authentication.TimeWindow = 15m0s
[         orderer]      General.Authentication.NoExpirationChecks = false
[         orderer]      General.MaxRecvMsgSize = 104857600
[         orderer]      General.MaxSendMsgSize = 104857600
[         orderer]      FileLedger.Location = "/opt/microfab/data/orderer/data"
[         orderer]      FileLedger.Prefix = ""
[         orderer]      Kafka.Retry.ShortInterval = 5s
[         orderer]      Kafka.Retry.ShortTotal = 10m0s
[         orderer]      Kafka.Retry.LongInterval = 5m0s
[         orderer]      Kafka.Retry.LongTotal = 12h0m0s
[         orderer]      Kafka.Retry.NetworkTimeouts.DialTimeout = 10s
[         orderer]      Kafka.Retry.NetworkTimeouts.ReadTimeout = 10s
[         orderer]      Kafka.Retry.NetworkTimeouts.WriteTimeout = 10s
[         orderer]      Kafka.Retry.Metadata.RetryMax = 3
[         orderer]      Kafka.Retry.Metadata.RetryBackoff = 250ms
[         orderer]      Kafka.Retry.Producer.RetryMax = 3
[         orderer]      Kafka.Retry.Producer.RetryBackoff = 100ms
[         orderer]      Kafka.Retry.Consumer.RetryBackoff = 2s
[         orderer]      Kafka.Verbose = false
[         orderer]      Kafka.Version = 0.10.2.0
[         orderer]      Kafka.TLS.Enabled = false
[         orderer]      Kafka.TLS.PrivateKey = ""
[         orderer]      Kafka.TLS.Certificate = ""
[         orderer]      Kafka.TLS.RootCAs = []
[         orderer]      Kafka.TLS.ClientAuthRequired = false
[         orderer]      Kafka.TLS.ClientRootCAs = []
[         orderer]      Kafka.TLS.TLSHandshakeTimeShift = 0s
[         orderer]      Kafka.SASLPlain.Enabled = false
[         orderer]      Kafka.SASLPlain.User = ""
[         orderer]      Kafka.SASLPlain.Password = ""
[         orderer]      Kafka.Topic.ReplicationFactor = 3
[         orderer]      Debug.BroadcastTraceDir = ""
[         orderer]      Debug.DeliverTraceDir = ""
[         orderer]      Consensus = map[SnapDir:/opt/microfab/data/orderer/data/etcdraft/snapshot WALDir:/opt/microfab/data/orderer/data/etcdraft/wal]
[         orderer]      Operations.ListenAddress = "0.0.0.0:2007"
[         orderer]      Operations.TLS.Enabled = false
[         orderer]      Operations.TLS.PrivateKey = ""
[         orderer]      Operations.TLS.Certificate = ""
[         orderer]      Operations.TLS.RootCAs = []
[         orderer]      Operations.TLS.ClientAuthRequired = false
[         orderer]      Operations.TLS.ClientRootCAs = []
[         orderer]      Operations.TLS.TLSHandshakeTimeShift = 0s
[         orderer]      Metrics.Provider = "prometheus"
[         orderer]      Metrics.Statsd.Network = "udp"
[         orderer]      Metrics.Statsd.Address = "127.0.0.1:8125"
[         orderer]      Metrics.Statsd.WriteInterval = 30s
[         orderer]      Metrics.Statsd.Prefix = ""
[         orderer]      ChannelParticipation.Enabled = false
[         orderer]      ChannelParticipation.MaxRequestBodySize = 1048576
[         orderer]      Admin.ListenAddress = "127.0.0.1:9443"
[         orderer]      Admin.TLS.Enabled = false
[         orderer]      Admin.TLS.PrivateKey = ""
[         orderer]      Admin.TLS.Certificate = ""
[         orderer]      Admin.TLS.RootCAs = []
[         orderer]      Admin.TLS.ClientAuthRequired = true
[         orderer]      Admin.TLS.ClientRootCAs = []
[         orderer]      Admin.TLS.TLSHandshakeTimeShift = 0s
[  sellersorgpeer] 2023-08-03 15:13:16.980 UTC 0001 INFO [nodeCmd] serve -> Starting peer:
[  sellersorgpeer]  Version: 2.4.6
[  sellersorgpeer]  Commit SHA: 83596078d
[  sellersorgpeer]  Go version: go1.18.2
[  sellersorgpeer]  OS/Arch: linux/amd64
[  sellersorgpeer]  Chaincode:
[  sellersorgpeer]   Base Docker Label: org.hyperledger.fabric
[  sellersorgpeer]   Docker Namespace: hyperledger
[  sellersorgpeer] 2023-08-03 15:13:16.981 UTC 0002 INFO [peer] getLocalAddress -> Auto-detected peer address: 172.17.0.2:2010
[  sellersorgpeer] 2023-08-03 15:13:16.981 UTC 0003 INFO [peer] getLocalAddress -> Host is 0.0.0.0 , falling back to auto-detected address: 172.17.0.2:2010
[  sellersorgpeer] 2023-08-03 15:13:16.985 UTC 0004 INFO [nodeCmd] initGrpcSemaphores -> concurrency limit for endorser service is 2500
[  sellersorgpeer] 2023-08-03 15:13:16.985 UTC 0005 INFO [nodeCmd] initGrpcSemaphores -> concurrency limit for deliver service is 2500
[  sellersorgpeer] 2023-08-03 15:13:16.985 UTC 0006 INFO [nodeCmd] initGrpcSemaphores -> concurrency limit for gateway service is 500
[  producersorgca] 2023/08/03 15:13:17 [INFO] Starting server in home directory: /opt/microfab/data/ca-producersorg
[  producersorgca] 2023/08/03 15:13:17 [INFO] Server Version: 1.5.2
[  producersorgca] 2023/08/03 15:13:17 [INFO] Server Levels: &{Identity:2 Affiliation:1 Certificate:1 Credential:1 RAInfo:1 Nonce:1}
[    sellersorgca] 2023/08/03 15:13:17 [INFO] Starting server in home directory: /opt/microfab/data/ca-sellersorg
[    sellersorgca] 2023/08/03 15:13:17 [INFO] Server Version: 1.5.2
[    sellersorgca] 2023/08/03 15:13:17 [INFO] Server Levels: &{Identity:2 Affiliation:1 Certificate:1 Credential:1 RAInfo:1 Nonce:1}
[    sellersorgca] 2023/08/03 15:13:17 [INFO] The CA key and certificate files already exist
[    sellersorgca] 2023/08/03 15:13:17 [INFO] Key file location: /opt/microfab/data/ca-sellersorg/ca-key.pem
[    sellersorgca] 2023/08/03 15:13:17 [INFO] Certificate file location: /opt/microfab/data/ca-sellersorg/ca-cert.pem
[  producersorgca] 2023/08/03 15:13:17 [INFO] The CA key and certificate files already exist
[  producersorgca] 2023/08/03 15:13:17 [INFO] Key file location: /opt/microfab/data/ca-producersorg/ca-key.pem
[  producersorgca] 2023/08/03 15:13:17 [INFO] Certificate file location: /opt/microfab/data/ca-producersorg/ca-cert.pem
[         orderer] 2023-08-03 15:13:17.006 UTC 0003 INFO [blkstorage] NewProvider -> Creating new file ledger directory at /opt/microfab/data/orderer/data/chains
[producersorgpeer] 2023-08-03 15:13:17.008 UTC 0007 INFO [certmonitor] trackCertExpiration -> The enrollment certificate will expire on 2033-07-31 15:08:16 +0000 UTC
[producersorgpeer] 2023-08-03 15:13:17.009 UTC 0008 INFO [ledgermgmt] NewLedgerMgr -> Initializing LedgerMgr
[         orderer] 2023-08-03 15:13:17.018 UTC 0004 INFO [orderer.common.server] Main -> Bootstrapping the system channel
[         orderer] 2023-08-03 15:13:17.019 UTC 0005 INFO [blkstorage] newBlockfileMgr -> Getting block information from block storage
[  sellersorgpeer] 2023-08-03 15:13:17.026 UTC 0007 INFO [certmonitor] trackCertExpiration -> The enrollment certificate will expire on 2033-07-31 15:08:16 +0000 UTC
[  sellersorgpeer] 2023-08-03 15:13:17.027 UTC 0008 INFO [ledgermgmt] NewLedgerMgr -> Initializing LedgerMgr
[         orderer] 2023-08-03 15:13:17.028 UTC 0006 INFO [orderer.common.server] initializeBootstrapChannel -> Initialized the system channel 'testchainid' from bootstrap block
[         orderer] 2023-08-03 15:13:17.036 UTC 0007 INFO [orderer.common.server] extractSystemChannel -> Found system channel config block, number: 0
[         orderer] 2023-08-03 15:13:17.036 UTC 0008 INFO [orderer.common.server] selectClusterBootBlock -> Cluster boot block is bootstrap (genesis) block; Blocks Header.Number system-channel=0, bootstrap=0
[         orderer] 2023-08-03 15:13:17.041 UTC 0009 INFO [orderer.common.server] Main -> Starting with system channel: testchainid, consensus type: solo
[         orderer] 2023-08-03 15:13:17.041 UTC 000a INFO [certmonitor] trackCertExpiration -> The enrollment certificate will expire on 2033-07-31 15:08:16 +0000 UTC
[producersorgpeer] 2023-08-03 15:13:17.045 UTC 0009 INFO [leveldbhelper] openDBAndCheckFormat -> DB is empty Setting db format as 2.0
[producersorgpeer] 2023-08-03 15:13:17.047 UTC 000a INFO [blkstorage] NewProvider -> Creating new file ledger directory at /opt/microfab/data/peer-producersorg/data/ledgersData/chains/chains
[         orderer] 2023-08-03 15:13:17.055 UTC 000b WARN [orderer.consensus.solo] HandleChain -> Use of the Solo orderer is deprecated and remains only for use in test environments but may be removed in the future.
[         orderer] 2023-08-03 15:13:17.055 UTC 000c INFO [orderer.commmon.multichannel] initSystemChannel -> Starting system channel 'testchainid' with genesis block hash 90a5dc40b5f52ad3f899400d401c3dcf8454f5c10a184f1f8692992c166cc8eb and orderer type solo
[         orderer] 2023-08-03 15:13:17.056 UTC 000d INFO [orderer.common.server] Main -> Starting orderer:
[         orderer]  Version: 2.4.6
[         orderer]  Commit SHA: 83596078d
[         orderer]  Go version: go1.18.2
[         orderer]  OS/Arch: linux/amd64
[         orderer] 2023-08-03 15:13:17.058 UTC 000e INFO [orderer.common.server] Main -> Beginning to serve requests
[  sellersorgpeer] 2023-08-03 15:13:17.071 UTC 0009 INFO [leveldbhelper] openDBAndCheckFormat -> DB is empty Setting db format as 2.0
[producersorgpeer] 2023-08-03 15:13:17.071 UTC 000b INFO [leveldbhelper] openDBAndCheckFormat -> DB is empty Setting db format as 2.0
[  sellersorgpeer] 2023-08-03 15:13:17.072 UTC 000a INFO [blkstorage] NewProvider -> Creating new file ledger directory at /opt/microfab/data/peer-sellersorg/data/ledgersData/chains/chains
[  sellersorgpeer] 2023-08-03 15:13:17.092 UTC 000b INFO [leveldbhelper] openDBAndCheckFormat -> DB is empty Setting db format as 2.0
2023/08/03 15:13:17 error waiting for CA: Get "http://localhost:2001/healthz": dial tcp 127.0.0.1:2001: connect: connection refused
2023/08/03 15:13:17 error waiting for CA: Get "http://localhost:2009/healthz": dial tcp 127.0.0.1:2009: connect: connection refused
[       microfabd] 2023/08/03 15:13:17 Created and started orderer for ordering organization Orderer
[producersorgpeer] 2023-08-03 15:13:17.191 UTC 000c INFO [couchdb] createDatabaseIfNotExist -> Created state database fabric__internal
[  sellersorgpeer] 2023-08-03 15:13:17.203 UTC 000c INFO [couchdb] createDatabaseIfNotExist -> Created state database fabric__internal
[producersorgpeer] 2023-08-03 15:13:17.256 UTC 000d INFO [ledgermgmt] NewLedgerMgr -> Initialized LedgerMgr
[producersorgpeer] 2023-08-03 15:13:17.258 UTC 000e INFO [gossip.service] New -> Initialize gossip with endpoint producersorgpeer-api.127-0-0-1.nip.io:8080
[  sellersorgpeer] 2023-08-03 15:13:17.260 UTC 000d INFO [ledgermgmt] NewLedgerMgr -> Initialized LedgerMgr
[producersorgpeer] 2023-08-03 15:13:17.261 UTC 000f INFO [gossip.gossip] New -> Creating gossip service with self membership of Endpoint: producersorgpeer-api.127-0-0-1.nip.io:8080, InternalEndpoint: producersorgpeer-api.127-0-0-1.nip.io:8080, PKI-ID: 02bb97e7d156781f19365424ae77027b3a4f0eba6a47d15843fb0e4f395bbfa9, Metadata: 
[producersorgpeer] 2023-08-03 15:13:17.261 UTC 0010 INFO [lifecycle] InitializeLocalChaincodes -> Initialized lifecycle cache with 0 already installed chaincodes
[producersorgpeer] 2023-08-03 15:13:17.261 UTC 0011 INFO [gossip.gossip] start -> Gossip instance producersorgpeer-api.127-0-0-1.nip.io:8080 started
[  sellersorgpeer] 2023-08-03 15:13:17.261 UTC 000e INFO [gossip.service] New -> Initialize gossip with endpoint sellersorgpeer-api.127-0-0-1.nip.io:8080
[producersorgpeer] 2023-08-03 15:13:17.262 UTC 0012 INFO [nodeCmd] computeChaincodeEndpoint -> Entering computeChaincodeEndpoint with peerHostname: 172.17.0.2
[producersorgpeer] 2023-08-03 15:13:17.262 UTC 0013 INFO [nodeCmd] computeChaincodeEndpoint -> Exit with ccEndpoint: 172.17.0.2:2003
[  sellersorgpeer] 2023-08-03 15:13:17.264 UTC 000f INFO [gossip.gossip] New -> Creating gossip service with self membership of Endpoint: sellersorgpeer-api.127-0-0-1.nip.io:8080, InternalEndpoint: sellersorgpeer-api.127-0-0-1.nip.io:8080, PKI-ID: def2a602fade420499ead957607ee21b8b31c6a48e11c40d8998b04ef9a94a32, Metadata: 
[  sellersorgpeer] 2023-08-03 15:13:17.265 UTC 0010 INFO [gossip.gossip] start -> Gossip instance sellersorgpeer-api.127-0-0-1.nip.io:8080 started
[  sellersorgpeer] 2023-08-03 15:13:17.265 UTC 0011 INFO [lifecycle] InitializeLocalChaincodes -> Initialized lifecycle cache with 0 already installed chaincodes
[producersorgpeer] 2023-08-03 15:13:17.265 UTC 0014 INFO [sccapi] DeploySysCC -> deploying system chaincode 'lscc'
[producersorgpeer] 2023-08-03 15:13:17.265 UTC 0015 INFO [sccapi] DeploySysCC -> deploying system chaincode 'cscc'
[producersorgpeer] 2023-08-03 15:13:17.265 UTC 0016 INFO [sccapi] DeploySysCC -> deploying system chaincode 'qscc'
[  sellersorgpeer] 2023-08-03 15:13:17.266 UTC 0012 INFO [nodeCmd] computeChaincodeEndpoint -> Entering computeChaincodeEndpoint with peerHostname: 172.17.0.2
[  sellersorgpeer] 2023-08-03 15:13:17.266 UTC 0013 INFO [nodeCmd] computeChaincodeEndpoint -> Exit with ccEndpoint: 172.17.0.2:2011
[producersorgpeer] 2023-08-03 15:13:17.266 UTC 0017 INFO [sccapi] DeploySysCC -> deploying system chaincode '_lifecycle'
[  sellersorgpeer] 2023-08-03 15:13:17.268 UTC 0014 INFO [sccapi] DeploySysCC -> deploying system chaincode 'lscc'
[producersorgpeer] 2023-08-03 15:13:17.266 UTC 0018 INFO [nodeCmd] serve -> Deployed system chaincodes
[producersorgpeer] 2023-08-03 15:13:17.266 UTC 0019 INFO [discovery] NewService -> Created with config TLS: false, authCacheMaxSize: 1000, authCachePurgeRatio: 0.750000
[producersorgpeer] 2023-08-03 15:13:17.266 UTC 001a INFO [nodeCmd] serve -> Discovery service activated
[producersorgpeer] 2023-08-03 15:13:17.266 UTC 001b INFO [nodeCmd] serve -> Starting peer with Gateway enabled
[  sellersorgpeer] 2023-08-03 15:13:17.269 UTC 0015 INFO [sccapi] DeploySysCC -> deploying system chaincode 'cscc'
[producersorgpeer] 2023-08-03 15:13:17.266 UTC 001c INFO [nodeCmd] serve -> Starting peer with ID=[producersorgpeer], network ID=[dev], address=[172.17.0.2:2002]
[  sellersorgpeer] 2023-08-03 15:13:17.269 UTC 0016 INFO [sccapi] DeploySysCC -> deploying system chaincode 'qscc'
[  sellersorgpeer] 2023-08-03 15:13:17.269 UTC 0017 INFO [sccapi] DeploySysCC -> deploying system chaincode '_lifecycle'
[  sellersorgpeer] 2023-08-03 15:13:17.269 UTC 0018 INFO [nodeCmd] serve -> Deployed system chaincodes
[producersorgpeer] 2023-08-03 15:13:17.267 UTC 001d INFO [nodeCmd] serve -> Started peer with ID=[producersorgpeer], network ID=[dev], address=[172.17.0.2:2002]
[producersorgpeer] 2023-08-03 15:13:17.268 UTC 001e INFO [kvledger] LoadPreResetHeight -> Loading prereset height from path [/opt/microfab/data/peer-producersorg/data/ledgersData/chains]
[producersorgpeer] 2023-08-03 15:13:17.268 UTC 001f INFO [blkstorage] preResetHtFiles -> No active channels passed
[  sellersorgpeer] 2023-08-03 15:13:17.270 UTC 0019 INFO [discovery] NewService -> Created with config TLS: false, authCacheMaxSize: 1000, authCachePurgeRatio: 0.750000
[  sellersorgpeer] 2023-08-03 15:13:17.270 UTC 001a INFO [nodeCmd] serve -> Discovery service activated
[  sellersorgpeer] 2023-08-03 15:13:17.270 UTC 001b INFO [nodeCmd] serve -> Starting peer with Gateway enabled
[  sellersorgpeer] 2023-08-03 15:13:17.271 UTC 001c INFO [nodeCmd] serve -> Starting peer with ID=[sellersorgpeer], network ID=[dev], address=[172.17.0.2:2010]
[  producersorgca] 2023/08/03 15:13:17 [INFO] Initialized sqlite3 database at /opt/microfab/data/ca-producersorg/fabric-ca-server.db
[  sellersorgpeer] 2023-08-03 15:13:17.271 UTC 001d INFO [nodeCmd] serve -> Started peer with ID=[sellersorgpeer], network ID=[dev], address=[172.17.0.2:2010]
[  sellersorgpeer] 2023-08-03 15:13:17.272 UTC 001e INFO [kvledger] LoadPreResetHeight -> Loading prereset height from path [/opt/microfab/data/peer-sellersorg/data/ledgersData/chains]
[  sellersorgpeer] 2023-08-03 15:13:17.272 UTC 001f INFO [blkstorage] preResetHtFiles -> No active channels passed
[    sellersorgca] 2023/08/03 15:13:17 [INFO] Initialized sqlite3 database at /opt/microfab/data/ca-sellersorg/fabric-ca-server.db
[  producersorgca] 2023/08/03 15:13:17 [INFO] The issuer key was successfully stored. The public key is at: /opt/microfab/data/ca-producersorg/IssuerPublicKey, secret key is at: /opt/microfab/data/ca-producersorg/msp/keystore/IssuerSecretKey
[  producersorgca] 2023/08/03 15:13:17 [INFO] Idemix issuer revocation public and secret keys were generated for CA 'producersorgca'
[  producersorgca] 2023/08/03 15:13:17 [INFO] The revocation key was successfully stored. The public key is at: /opt/microfab/data/ca-producersorg/IssuerRevocationPublicKey, private key is at: /opt/microfab/data/ca-producersorg/msp/keystore/IssuerRevocationPrivateKey
[    sellersorgca] 2023/08/03 15:13:17 [INFO] The issuer key was successfully stored. The public key is at: /opt/microfab/data/ca-sellersorg/IssuerPublicKey, secret key is at: /opt/microfab/data/ca-sellersorg/msp/keystore/IssuerSecretKey
[  producersorgca] 2023/08/03 15:13:17 [INFO] Home directory for default CA: /opt/microfab/data/ca-producersorg
[  producersorgca] 2023/08/03 15:13:17 [INFO] Operation Server Listening on [::]:2009
[  producersorgca] 2023/08/03 15:13:17 [INFO] Listening on http://0.0.0.0:2008
[    sellersorgca] 2023/08/03 15:13:17 [INFO] Idemix issuer revocation public and secret keys were generated for CA 'sellersorgca'
[    sellersorgca] 2023/08/03 15:13:17 [INFO] The revocation key was successfully stored. The public key is at: /opt/microfab/data/ca-sellersorg/IssuerRevocationPublicKey, private key is at: /opt/microfab/data/ca-sellersorg/msp/keystore/IssuerRevocationPrivateKey
2023/08/03 15:13:17 error waiting for CA: Get "http://localhost:2001/healthz": dial tcp 127.0.0.1:2001: connect: connection refused
[    sellersorgca] 2023/08/03 15:13:17 [INFO] Home directory for default CA: /opt/microfab/data/ca-sellersorg
[    sellersorgca] 2023/08/03 15:13:17 [INFO] Operation Server Listening on [::]:2001
[    sellersorgca] 2023/08/03 15:13:17 [INFO] Listening on http://0.0.0.0:2000
[producersorgpeer] 2023-08-03 15:13:17.380 UTC 0020 INFO [endorser] callChaincode -> finished chaincode: cscc duration: 0ms channel= txID=e73d790c
[producersorgpeer] 2023-08-03 15:13:17.380 UTC 0021 INFO [comm.grpc.server] 1 -> unary call completed grpc.service=protos.Endorser grpc.method=ProcessProposal grpc.request_deadline=2023-08-03T15:13:47.377Z grpc.peer_address=127.0.0.1:56176 grpc.code=OK grpc.call_duration=2.764934ms
[       microfabd] 2023/08/03 15:13:17 Created and started peer for endorsing organization ProducersOrg
[  sellersorgpeer] 2023-08-03 15:13:17.383 UTC 0020 INFO [endorser] callChaincode -> finished chaincode: cscc duration: 1ms channel= txID=ec7d9221
[  sellersorgpeer] 2023-08-03 15:13:17.383 UTC 0021 INFO [comm.grpc.server] 1 -> unary call completed grpc.service=protos.Endorser grpc.method=ProcessProposal grpc.request_deadline=2023-08-03T15:13:47.377Z grpc.peer_address=127.0.0.1:52666 grpc.code=OK grpc.call_duration=5.316431ms
[       microfabd] 2023/08/03 15:13:17 Created and started peer for endorsing organization SellersOrg
[  producersorgca] 2023/08/03 15:13:17 [INFO] signed certificate with serial number 379362407337876806474819551431127587515853409081
[  producersorgca] 2023/08/03 15:13:17 [INFO] 127.0.0.1:58274 POST /enroll 201 0 "OK"
[       microfabd] 2023/08/03 15:13:17 Created and started CA for endorsing organization ProducersOrg
[    sellersorgca] 2023/08/03 15:13:17 [INFO] signed certificate with serial number 631973055168546088009009874756221469123232148155
[    sellersorgca] 2023/08/03 15:13:17 [INFO] 127.0.0.1:34056 POST /enroll 201 0 "OK"
[       microfabd] 2023/08/03 15:13:17 Created and started CA for endorsing organization SellersOrg
[       microfabd] 2023/08/03 15:13:17 Creating and starting console ...
[         console] 2023/08/03 15:13:17 Created new console...
[         console] 2023/08/03 15:13:17 [mbw] RegisterOrganization &{Orderer 0xc0005e3050 0xc0001b6360 <nil> OrdererMSP}
[         console] 2023/08/03 15:13:17 [mbw] RegisterOrganization &{ProducersOrg 0xc0005c3080 0xc000202390 0xc0005e2090 ProducersOrgMSP}
[         console] 2023/08/03 15:13:17 [mbw] RegisterOrganization &{SellersOrg 0xc00002c750 0xc00002da40 0xc000621230 SellersOrgMSP}
[       microfabd] 2023/08/03 15:13:17 Created and started console
[       microfabd] 2023/08/03 15:13:17 Creating and starting proxy ...
[       microfabd] 2023/08/03 15:13:17 Created and started proxy
[       microfabd] 2023/08/03 15:13:17 Creating and joining channel mango-channel ...
[       microfabd] 2023/08/03 15:13:17 Creating channel mango-channel ...
[         orderer] 2023-08-03 15:13:17.792 UTC 000f INFO [comm.grpc.server] 1 -> streaming call completed grpc.service=orderer.AtomicBroadcast grpc.method=Broadcast grpc.request_deadline=2023-08-03T15:13:47.772Z grpc.peer_address=127.0.0.1:34646 grpc.code=OK grpc.call_duration=19.172152ms
[         orderer] 2023-08-03 15:13:17.797 UTC 0010 INFO [blkstorage] newBlockfileMgr -> Getting block information from block storage
[         orderer] 2023-08-03 15:13:17.803 UTC 0011 WARN [orderer.consensus.solo] HandleChain -> Use of the Solo orderer is deprecated and remains only for use in test environments but may be removed in the future.
[         orderer] 2023-08-03 15:13:17.803 UTC 0012 INFO [orderer.commmon.multichannel] newChain -> Created and started new channel mango-channel
[         orderer] 2023-08-03 15:13:17.806 UTC 0013 INFO [comm.grpc.server] 1 -> streaming call completed grpc.service=orderer.AtomicBroadcast grpc.method=Deliver grpc.request_deadline=2023-08-03T15:13:47.794Z grpc.peer_address=127.0.0.1:34646 grpc.code=OK grpc.call_duration=12.248832ms
[         orderer] 2023-08-03 15:13:17.810 UTC 0014 INFO [comm.grpc.server] 1 -> streaming call completed grpc.service=orderer.AtomicBroadcast grpc.method=Deliver grpc.request_deadline=2023-08-03T15:13:47.808Z grpc.peer_address=127.0.0.1:34646 grpc.code=OK grpc.call_duration=1.360928ms
[         orderer] 2023-08-03 15:13:17.811 UTC 0015 INFO [comm.grpc.server] 1 -> streaming call completed grpc.service=orderer.AtomicBroadcast grpc.method=Deliver grpc.request_deadline=2023-08-03T15:13:47.81Z grpc.peer_address=127.0.0.1:34646 grpc.code=OK grpc.call_duration=1.121647ms
[         orderer] 2023-08-03 15:13:17.827 UTC 0016 INFO [comm.grpc.server] 1 -> streaming call completed grpc.service=orderer.AtomicBroadcast grpc.method=Broadcast grpc.request_deadline=2023-08-03T15:13:47.814Z grpc.peer_address=127.0.0.1:34646 grpc.code=OK grpc.call_duration=13.404894ms
[       microfabd] 2023/08/03 15:13:17 Created channel mango-channel
[       microfabd] 2023/08/03 15:13:17 Joining channel mango-channel on peer for endorsing organization SellersOrg ...
[       microfabd] 2023/08/03 15:13:17 Joining channel mango-channel on peer for endorsing organization ProducersOrg ...
[producersorgpeer] 2023-08-03 15:13:17.836 UTC 0022 INFO [ledgermgmt] CreateLedger -> Creating ledger [mango-channel] with genesis block
[  sellersorgpeer] 2023-08-03 15:13:17.838 UTC 0022 INFO [ledgermgmt] CreateLedger -> Creating ledger [mango-channel] with genesis block
[producersorgpeer] 2023-08-03 15:13:17.839 UTC 0023 INFO [blkstorage] newBlockfileMgr -> Getting block information from block storage
[  sellersorgpeer] 2023-08-03 15:13:17.841 UTC 0023 INFO [blkstorage] newBlockfileMgr -> Getting block information from block storage
[producersorgpeer] 2023-08-03 15:13:17.860 UTC 0024 INFO [couchdb] createDatabaseIfNotExist -> Created state database mango-channel_
[  sellersorgpeer] 2023-08-03 15:13:17.871 UTC 0024 INFO [couchdb] createDatabaseIfNotExist -> Created state database mango-channel_
[producersorgpeer] 2023-08-03 15:13:17.921 UTC 0025 INFO [couchdb] createDatabaseIfNotExist -> Created state database mango-channel__lifecycle
[  sellersorgpeer] 2023-08-03 15:13:17.927 UTC 0025 INFO [couchdb] createDatabaseIfNotExist -> Created state database mango-channel__lifecycle
[  sellersorgpeer] 2023-08-03 15:13:17.994 UTC 0026 INFO [kvledger] commit -> [mango-channel] Committed block [0] with 1 transaction(s) in 52ms (state_validation=0ms block_and_pvtdata_commit=3ms state_commit=48ms) commitHash=[]
[  sellersorgpeer] 2023-08-03 15:13:17.994 UTC 0027 INFO [kvledger] updateLedgerStatus -> Updating ledger [mango-channel] status to [ACTIVE]
[producersorgpeer] 2023-08-03 15:13:17.994 UTC 0026 INFO [kvledger] commit -> [mango-channel] Committed block [0] with 1 transaction(s) in 58ms (state_validation=0ms block_and_pvtdata_commit=3ms state_commit=52ms) commitHash=[]
[producersorgpeer] 2023-08-03 15:13:17.995 UTC 0027 INFO [kvledger] updateLedgerStatus -> Updating ledger [mango-channel] status to [ACTIVE]
[  sellersorgpeer] 2023-08-03 15:13:17.995 UTC 0028 INFO [ledgermgmt] CreateLedger -> Created ledger [mango-channel] with genesis block
[producersorgpeer] 2023-08-03 15:13:17.996 UTC 0028 INFO [ledgermgmt] CreateLedger -> Created ledger [mango-channel] with genesis block
[  sellersorgpeer] 2023-08-03 15:13:18.009 UTC 0029 INFO [gossip.gossip] JoinChan -> Joining gossip network of channel mango-channel with 2 organizations
[  sellersorgpeer] 2023-08-03 15:13:18.009 UTC 002a INFO [gossip.gossip] learnAnchorPeers -> No configured anchor peers of ProducersOrgMSP for channel mango-channel to learn about
[  sellersorgpeer] 2023-08-03 15:13:18.009 UTC 002b INFO [gossip.gossip] learnAnchorPeers -> No configured anchor peers of SellersOrgMSP for channel mango-channel to learn about
[  sellersorgpeer] 2023-08-03 15:13:18.009 UTC 002c INFO [gateway] configUpdate -> Updating orderer config channel=mango-channel
[  sellersorgpeer] 2023-08-03 15:13:18.010 UTC 002d INFO [gossip.state] NewGossipStateProvider -> Updating metadata information for channel mango-channel, current ledger sequence is at = 0, next expected block is = 1
[  sellersorgpeer] 2023-08-03 15:13:18.010 UTC 002e INFO [deliveryClient] StartDeliverForChannel -> This peer will retrieve blocks from ordering service and disseminate to other peers in the organization for channel mango-channel
[  sellersorgpeer] 2023-08-03 15:13:18.010 UTC 002f INFO [endorser] callChaincode -> finished chaincode: cscc duration: 179ms channel= txID=8f921adb
[  sellersorgpeer] 2023-08-03 15:13:18.011 UTC 0030 INFO [comm.grpc.server] 1 -> unary call completed grpc.service=protos.Endorser grpc.method=ProcessProposal grpc.request_deadline=2023-08-03T15:13:47.829Z grpc.peer_address=127.0.0.1:52668 grpc.code=OK grpc.call_duration=180.8517ms
[       microfabd] 2023/08/03 15:13:18 Joined channel mango-channel on peer for endorsing organization SellersOrg
[       microfabd] 2023/08/03 15:13:18 Joined channel mango-channel on peer for endorsing organization ProducersOrg
[       microfabd] 2023/08/03 15:13:18 Created and joined channel mango-channel
[producersorgpeer] 2023-08-03 15:13:18.010 UTC 0029 INFO [gossip.gossip] JoinChan -> Joining gossip network of channel mango-channel with 2 organizations
[producersorgpeer] 2023-08-03 15:13:18.010 UTC 002a INFO [gossip.gossip] learnAnchorPeers -> No configured anchor peers of SellersOrgMSP for channel mango-channel to learn about
[producersorgpeer] 2023-08-03 15:13:18.010 UTC 002b INFO [gossip.gossip] learnAnchorPeers -> No configured anchor peers of ProducersOrgMSP for channel mango-channel to learn about
[producersorgpeer] 2023-08-03 15:13:18.010 UTC 002c INFO [gateway] configUpdate -> Updating orderer config channel=mango-channel
[producersorgpeer] 2023-08-03 15:13:18.011 UTC 002d INFO [gossip.state] NewGossipStateProvider -> Updating metadata information for channel mango-channel, current ledger sequence is at = 0, next expected block is = 1
[producersorgpeer] 2023-08-03 15:13:18.011 UTC 002e INFO [deliveryClient] StartDeliverForChannel -> This peer will retrieve blocks from ordering service and disseminate to other peers in the organization for channel mango-channel
[producersorgpeer] 2023-08-03 15:13:18.012 UTC 002f INFO [endorser] callChaincode -> finished chaincode: cscc duration: 181ms channel= txID=8c7f5123
[producersorgpeer] 2023-08-03 15:13:18.012 UTC 0030 INFO [comm.grpc.server] 1 -> unary call completed grpc.service=protos.Endorser grpc.method=ProcessProposal grpc.request_deadline=2023-08-03T15:13:47.829Z grpc.peer_address=127.0.0.1:56178 grpc.code=OK grpc.call_duration=182.390626ms
[       microfabd] 2023/08/03 15:13:18 Microfab started in 2461ms
[  sellersorgpeer] 2023-08-03 15:13:18.028 UTC 0031 INFO [gossip.privdata] StoreBlock -> Received block [1] from buffer channel=mango-channel
[producersorgpeer] 2023-08-03 15:13:18.028 UTC 0031 INFO [gossip.privdata] StoreBlock -> Received block [1] from buffer channel=mango-channel
[producersorgpeer] 2023-08-03 15:13:18.040 UTC 0032 INFO [gossip.gossip] JoinChan -> Joining gossip network of channel mango-channel with 2 organizations
[producersorgpeer] 2023-08-03 15:13:18.040 UTC 0033 INFO [gossip.gossip] learnAnchorPeers -> Learning about the configured anchor peers of SellersOrgMSP for channel mango-channel: [{sellersorgpeer-api.127-0-0-1.nip.io 8080}]
[producersorgpeer] 2023-08-03 15:13:18.040 UTC 0034 INFO [gossip.gossip] learnAnchorPeers -> Learning about the configured anchor peers of ProducersOrgMSP for channel mango-channel: [{producersorgpeer-api.127-0-0-1.nip.io 8080}]
[producersorgpeer] 2023-08-03 15:13:18.040 UTC 0035 INFO [gossip.gossip] learnAnchorPeers -> Anchor peer for channel mango-channel with same endpoint, skipping connecting to myself
[producersorgpeer] 2023-08-03 15:13:18.040 UTC 0036 INFO [gateway] configUpdate -> Updating orderer config channel=mango-channel
[producersorgpeer] 2023-08-03 15:13:18.040 UTC 0037 INFO [committer.txvalidator] Validate -> [mango-channel] Validated block [1] in 11ms
[  sellersorgpeer] 2023-08-03 15:13:18.041 UTC 0032 INFO [gossip.gossip] JoinChan -> Joining gossip network of channel mango-channel with 2 organizations
[  sellersorgpeer] 2023-08-03 15:13:18.041 UTC 0033 INFO [gossip.gossip] learnAnchorPeers -> Learning about the configured anchor peers of ProducersOrgMSP for channel mango-channel: [{producersorgpeer-api.127-0-0-1.nip.io 8080}]
[  sellersorgpeer] 2023-08-03 15:13:18.041 UTC 0034 INFO [gossip.gossip] learnAnchorPeers -> Learning about the configured anchor peers of SellersOrgMSP for channel mango-channel: [{sellersorgpeer-api.127-0-0-1.nip.io 8080}]
[  sellersorgpeer] 2023-08-03 15:13:18.041 UTC 0035 INFO [gossip.gossip] learnAnchorPeers -> Anchor peer for channel mango-channel with same endpoint, skipping connecting to myself
[  sellersorgpeer] 2023-08-03 15:13:18.041 UTC 0036 INFO [gateway] configUpdate -> Updating orderer config channel=mango-channel
[  sellersorgpeer] 2023-08-03 15:13:18.041 UTC 0037 INFO [committer.txvalidator] Validate -> [mango-channel] Validated block [1] in 12ms
[  sellersorgpeer] 2023-08-03 15:13:18.073 UTC 0038 INFO [kvledger] commit -> [mango-channel] Committed block [1] with 1 transaction(s) in 31ms (state_validation=0ms block_and_pvtdata_commit=4ms state_commit=25ms) commitHash=[47dc540c94ceb704a23875c11273e16bb0b8a87aed84de911f2133568115f254]
[producersorgpeer] 2023-08-03 15:13:18.074 UTC 0038 INFO [kvledger] commit -> [mango-channel] Committed block [1] with 1 transaction(s) in 33ms (state_validation=0ms block_and_pvtdata_commit=4ms state_commit=26ms) commitHash=[47dc540c94ceb704a23875c11273e16bb0b8a87aed84de911f2133568115f254]
[producersorgpeer] 2023-08-03 15:13:18.203 UTC 0039 INFO [comm.grpc.server] 1 -> unary call completed grpc.service=gossip.Gossip grpc.method=Ping grpc.request_deadline=2023-08-03T15:13:20.202Z grpc.peer_address=127.0.0.1:56192 grpc.code=OK grpc.call_duration=92.52µs
[producersorgpeer] 2023-08-03 15:13:18.207 UTC 003a INFO [gossip.comm] GossipStream -> Peer def2a602fade420499ead957607ee21b8b31c6a48e11c40d8998b04ef9a94a32 (127.0.0.1:56192) probed us
[producersorgpeer] 2023-08-03 15:13:18.208 UTC 003b INFO [comm.grpc.server] 1 -> streaming call completed grpc.service=gossip.Gossip grpc.method=GossipStream grpc.request_deadline=2023-08-03T15:13:28.204Z grpc.peer_address=127.0.0.1:56192 grpc.code=OK grpc.call_duration=3.378757ms
[producersorgpeer] 2023-08-03 15:13:18.217 UTC 003c INFO [comm.grpc.server] 1 -> unary call completed grpc.service=gossip.Gossip grpc.method=Ping grpc.request_deadline=2023-08-03T15:13:20.216Z grpc.peer_address=127.0.0.1:56192 grpc.code=OK grpc.call_duration=411.284µs
[  sellersorgpeer] 2023-08-03 15:13:18.241 UTC 0039 INFO [comm.grpc.server] 1 -> unary call completed grpc.service=gossip.Gossip grpc.method=Ping grpc.request_deadline=2023-08-03T15:13:20.241Z grpc.peer_address=127.0.0.1:52678 grpc.code=OK grpc.call_duration=140.477µs
[  sellersorgpeer] 2023-08-03 15:13:18.244 UTC 003a INFO [gossip.comm] GossipStream -> Peer 02bb97e7d156781f19365424ae77027b3a4f0eba6a47d15843fb0e4f395bbfa9 (127.0.0.1:52678) probed us
[  sellersorgpeer] 2023-08-03 15:13:18.244 UTC 003b INFO [comm.grpc.server] 1 -> streaming call completed grpc.service=gossip.Gossip grpc.method=GossipStream grpc.request_deadline=2023-08-03T15:13:28.242Z grpc.peer_address=127.0.0.1:52678 grpc.code=OK grpc.call_duration=1.373034ms
[  sellersorgpeer] 2023-08-03 15:13:23.010 UTC 003c INFO [gossip.channel] reportMembershipChanges -> [[mango-channel] Membership view has changed. peers went online:  [[producersorgpeer-api.127-0-0-1.nip.io:8080 ]] , current view:  [[producersorgpeer-api.127-0-0-1.nip.io:8080 ]]]
[producersorgpeer] 2023-08-03 15:13:23.010 UTC 003d INFO [gossip.channel] reportMembershipChanges -> [[mango-channel] Membership view has changed. peers went online:  [[sellersorgpeer-api.127-0-0-1.nip.io:8080 ]] , current view:  [[sellersorgpeer-api.127-0-0-1.nip.io:8080 ]]]
```

# stop microfab
```
control + c
```
```
sudo docker container prune
```