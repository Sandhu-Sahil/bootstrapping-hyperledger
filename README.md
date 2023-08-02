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
    "port": 8080,
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
    ]
}'

```

# runnning microfab
```
sudo docker run -e MICROFAB_CONFIG -p 8080:8080 ibmcom/ibp-microfab

```

# output
```
[       microfabd] 2023/08/01 16:11:45 Starting Microfab ...
[       microfabd] 2023/08/01 16:11:45 MBW
[       microfabd] 2023/08/01 16:11:45 Creating endorsing organization Org1 ...
[       microfabd] 2023/08/01 16:11:45 Creating ordering organization Orderer ...
[       microfabd] 2023/08/01 16:11:45 Created ordering organization Orderer
[       microfabd] 2023/08/01 16:11:45 Created endorsing organization Org1
[       microfabd] 2023/08/01 16:11:45 Waiting for CouchDB to start ...
[       microfabd] 2023/08/01 16:11:47 CouchDB has started
[       microfabd] 2023/08/01 16:11:47 Creating and starting CA for endorsing organization Org1 ...
[       microfabd] 2023/08/01 16:11:47 Creating and starting orderer for ordering organization Orderer ...
[       microfabd] 2023/08/01 16:11:47 Creating and starting peer for endorsing organization Org1 ...
[       microfabd] 2023/08/01 16:11:47 Creating and starting CouchDB proxy for endorsing organization Org1 ...
[start --boot admin:adminpw --ca.certfile /opt/microfab/data/ca-org1/ca-cert.pem --ca.keyfile /opt/microfab/data/ca-org1/ca-key.pem --port 2000 --operations.listenaddress 0.0.0.0:2001 --ca.name org1ca][          org1ca] 2023/08/01 16:11:47 [INFO] Created default configuration file at /opt/microfab/data/ca-org1/fabric-ca-server-config.yaml
[         orderer] 2023-08-01 16:11:47.150 UTC 0001 INFO [localconfig] completeInitialization -> Kafka.Version unset, setting to 0.10.2.0
[         orderer] 2023-08-01 16:11:47.150 UTC 0002 INFO [orderer.common.server] prettyPrintStruct -> Orderer config values:
[         orderer]      General.ListenAddress = "0.0.0.0"
[         orderer]      General.ListenPort = 2002
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
[         orderer]      Operations.ListenAddress = "0.0.0.0:2003"
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
[        org1peer] 2023-08-01 16:11:47.178 UTC 0001 INFO [nodeCmd] serve -> Starting peer:
[        org1peer]  Version: 2.4.6
[        org1peer]  Commit SHA: 83596078d
[        org1peer]  Go version: go1.18.2
[        org1peer]  OS/Arch: linux/amd64
[        org1peer]  Chaincode:
[        org1peer]   Base Docker Label: org.hyperledger.fabric
[        org1peer]   Docker Namespace: hyperledger
[        org1peer] 2023-08-01 16:11:47.179 UTC 0002 INFO [peer] getLocalAddress -> Auto-detected peer address: 172.17.0.2:2004
[        org1peer] 2023-08-01 16:11:47.179 UTC 0003 INFO [peer] getLocalAddress -> Host is 0.0.0.0 , falling back to auto-detected address: 172.17.0.2:2004
[         orderer] 2023-08-01 16:11:47.180 UTC 0003 INFO [blkstorage] NewProvider -> Creating new file ledger directory at /opt/microfab/data/orderer/data/chains
[        org1peer] 2023-08-01 16:11:47.181 UTC 0004 INFO [nodeCmd] initGrpcSemaphores -> concurrency limit for endorser service is 2500
[        org1peer] 2023-08-01 16:11:47.181 UTC 0005 INFO [nodeCmd] initGrpcSemaphores -> concurrency limit for deliver service is 2500
[        org1peer] 2023-08-01 16:11:47.181 UTC 0006 INFO [nodeCmd] initGrpcSemaphores -> concurrency limit for gateway service is 500
[         orderer] 2023-08-01 16:11:47.188 UTC 0004 INFO [orderer.common.server] Main -> Bootstrapping the system channel
[         orderer] 2023-08-01 16:11:47.190 UTC 0005 INFO [blkstorage] newBlockfileMgr -> Getting block information from block storage
[         orderer] 2023-08-01 16:11:47.195 UTC 0006 INFO [orderer.common.server] initializeBootstrapChannel -> Initialized the system channel 'testchainid' from bootstrap block
[         orderer] 2023-08-01 16:11:47.202 UTC 0007 INFO [orderer.common.server] extractSystemChannel -> Found system channel config block, number: 0
[         orderer] 2023-08-01 16:11:47.203 UTC 0008 INFO [orderer.common.server] selectClusterBootBlock -> Cluster boot block is bootstrap (genesis) block; Blocks Header.Number system-channel=0, bootstrap=0
[        org1peer] 2023-08-01 16:11:47.204 UTC 0007 INFO [certmonitor] trackCertExpiration -> The enrollment certificate will expire on 2033-07-29 16:06:47 +0000 UTC
[        org1peer] 2023-08-01 16:11:47.205 UTC 0008 INFO [ledgermgmt] NewLedgerMgr -> Initializing LedgerMgr
[          org1ca] 2023/08/01 16:11:47 [INFO] Starting server in home directory: /opt/microfab/data/ca-org1
[          org1ca] 2023/08/01 16:11:47 [INFO] Server Version: 1.5.2
[          org1ca] 2023/08/01 16:11:47 [INFO] Server Levels: &{Identity:2 Affiliation:1 Certificate:1 Credential:1 RAInfo:1 Nonce:1}
[          org1ca] 2023/08/01 16:11:47 [INFO] The CA key and certificate files already exist
[          org1ca] 2023/08/01 16:11:47 [INFO] Key file location: /opt/microfab/data/ca-org1/ca-key.pem
[          org1ca] 2023/08/01 16:11:47 [INFO] Certificate file location: /opt/microfab/data/ca-org1/ca-cert.pem
[         orderer] 2023-08-01 16:11:47.209 UTC 0009 INFO [orderer.common.server] Main -> Starting with system channel: testchainid, consensus type: solo
[         orderer] 2023-08-01 16:11:47.209 UTC 000a INFO [certmonitor] trackCertExpiration -> The enrollment certificate will expire on 2033-07-29 16:06:47 +0000 UTC
[         orderer] 2023-08-01 16:11:47.217 UTC 000b WARN [orderer.consensus.solo] HandleChain -> Use of the Solo orderer is deprecated and remains only for use in test environments but may be removed in the future.
[         orderer] 2023-08-01 16:11:47.217 UTC 000c INFO [orderer.commmon.multichannel] initSystemChannel -> Starting system channel 'testchainid' with genesis block hash 025cbf410e674ba30a8d8195b9159433049cf9a205477018a9d5dd42fdb9eb0c and orderer type solo
[         orderer] 2023-08-01 16:11:47.219 UTC 000d INFO [orderer.common.server] Main -> Starting orderer:
[         orderer]  Version: 2.4.6
[         orderer]  Commit SHA: 83596078d
[         orderer]  Go version: go1.18.2
[         orderer]  OS/Arch: linux/amd64
[         orderer] 2023-08-01 16:11:47.219 UTC 000e INFO [orderer.common.server] Main -> Beginning to serve requests
[        org1peer] 2023-08-01 16:11:47.230 UTC 0009 INFO [leveldbhelper] openDBAndCheckFormat -> DB is empty Setting db format as 2.0
[        org1peer] 2023-08-01 16:11:47.231 UTC 000a INFO [blkstorage] NewProvider -> Creating new file ledger directory at /opt/microfab/data/peer-org1/data/ledgersData/chains/chains
[        org1peer] 2023-08-01 16:11:47.250 UTC 000b INFO [leveldbhelper] openDBAndCheckFormat -> DB is empty Setting db format as 2.0
2023/08/01 16:11:47 error waiting for CA: Get "http://localhost:2001/healthz": dial tcp 127.0.0.1:2001: connect: connection refused
[       microfabd] 2023/08/01 16:11:47 Created and started orderer for ordering organization Orderer
[        org1peer] 2023-08-01 16:11:47.346 UTC 000c INFO [couchdb] createDatabaseIfNotExist -> Created state database fabric__internal
[        org1peer] 2023-08-01 16:11:47.400 UTC 000d INFO [ledgermgmt] NewLedgerMgr -> Initialized LedgerMgr
[        org1peer] 2023-08-01 16:11:47.402 UTC 000e INFO [gossip.service] New -> Initialize gossip with endpoint org1peer-api.127-0-0-1.nip.io:8080
[        org1peer] 2023-08-01 16:11:47.404 UTC 000f INFO [gossip.gossip] New -> Creating gossip service with self membership of Endpoint: org1peer-api.127-0-0-1.nip.io:8080, InternalEndpoint: org1peer-api.127-0-0-1.nip.io:8080, PKI-ID: 1e1539659e09affd5dc4af002bface45b2881cdceafb484d3340f74a9513ab19, Metadata: 
[        org1peer] 2023-08-01 16:11:47.405 UTC 0010 INFO [gossip.gossip] start -> Gossip instance org1peer-api.127-0-0-1.nip.io:8080 started
[        org1peer] 2023-08-01 16:11:47.405 UTC 0011 INFO [lifecycle] InitializeLocalChaincodes -> Initialized lifecycle cache with 0 already installed chaincodes
[        org1peer] 2023-08-01 16:11:47.406 UTC 0012 INFO [nodeCmd] computeChaincodeEndpoint -> Entering computeChaincodeEndpoint with peerHostname: 172.17.0.2
[        org1peer] 2023-08-01 16:11:47.406 UTC 0013 INFO [nodeCmd] computeChaincodeEndpoint -> Exit with ccEndpoint: 172.17.0.2:2005
[        org1peer] 2023-08-01 16:11:47.407 UTC 0014 INFO [sccapi] DeploySysCC -> deploying system chaincode 'lscc'
[        org1peer] 2023-08-01 16:11:47.408 UTC 0015 INFO [sccapi] DeploySysCC -> deploying system chaincode 'cscc'
[        org1peer] 2023-08-01 16:11:47.408 UTC 0016 INFO [sccapi] DeploySysCC -> deploying system chaincode 'qscc'
[        org1peer] 2023-08-01 16:11:47.408 UTC 0017 INFO [sccapi] DeploySysCC -> deploying system chaincode '_lifecycle'
[        org1peer] 2023-08-01 16:11:47.408 UTC 0018 INFO [nodeCmd] serve -> Deployed system chaincodes
[        org1peer] 2023-08-01 16:11:47.409 UTC 0019 INFO [discovery] NewService -> Created with config TLS: false, authCacheMaxSize: 1000, authCachePurgeRatio: 0.750000
[        org1peer] 2023-08-01 16:11:47.409 UTC 001a INFO [nodeCmd] serve -> Discovery service activated
[        org1peer] 2023-08-01 16:11:47.409 UTC 001b INFO [nodeCmd] serve -> Starting peer with Gateway enabled
[        org1peer] 2023-08-01 16:11:47.409 UTC 001c INFO [nodeCmd] serve -> Starting peer with ID=[org1peer], network ID=[dev], address=[172.17.0.2:2004]
[        org1peer] 2023-08-01 16:11:47.412 UTC 001d INFO [nodeCmd] serve -> Started peer with ID=[org1peer], network ID=[dev], address=[172.17.0.2:2004]
[        org1peer] 2023-08-01 16:11:47.412 UTC 001e INFO [kvledger] LoadPreResetHeight -> Loading prereset height from path [/opt/microfab/data/peer-org1/data/ledgersData/chains]
[        org1peer] 2023-08-01 16:11:47.412 UTC 001f INFO [blkstorage] preResetHtFiles -> No active channels passed
[          org1ca] 2023/08/01 16:11:47 [INFO] Initialized sqlite3 database at /opt/microfab/data/ca-org1/fabric-ca-server.db
[          org1ca] 2023/08/01 16:11:47 [INFO] The issuer key was successfully stored. The public key is at: /opt/microfab/data/ca-org1/IssuerPublicKey, secret key is at: /opt/microfab/data/ca-org1/msp/keystore/IssuerSecretKey
[          org1ca] 2023/08/01 16:11:47 [INFO] Idemix issuer revocation public and secret keys were generated for CA 'org1ca'
[          org1ca] 2023/08/01 16:11:47 [INFO] The revocation key was successfully stored. The public key is at: /opt/microfab/data/ca-org1/IssuerRevocationPublicKey, private key is at: /opt/microfab/data/ca-org1/msp/keystore/IssuerRevocationPrivateKey
[          org1ca] 2023/08/01 16:11:47 [INFO] Home directory for default CA: /opt/microfab/data/ca-org1
[          org1ca] 2023/08/01 16:11:47 [INFO] Operation Server Listening on [::]:2001
[          org1ca] 2023/08/01 16:11:47 [INFO] Listening on http://0.0.0.0:2000
[        org1peer] 2023-08-01 16:11:47.597 UTC 0020 INFO [endorser] callChaincode -> finished chaincode: cscc duration: 0ms channel= txID=bd5ff069
[        org1peer] 2023-08-01 16:11:47.597 UTC 0021 INFO [comm.grpc.server] 1 -> unary call completed grpc.service=protos.Endorser grpc.method=ProcessProposal grpc.request_deadline=2023-08-01T16:12:17.594Z grpc.peer_address=127.0.0.1:54724 grpc.code=OK grpc.call_duration=2.186954ms
[       microfabd] 2023/08/01 16:11:47 Created and started peer for endorsing organization Org1
[          org1ca] 2023/08/01 16:11:47 [INFO] signed certificate with serial number 56290940600618397715027338714747812573198724209
[          org1ca] 2023/08/01 16:11:47 [INFO] 127.0.0.1:53598 POST /enroll 201 0 "OK"
[       microfabd] 2023/08/01 16:11:47 Created and started CA for endorsing organization Org1
[       microfabd] 2023/08/01 16:11:47 Creating and starting console ...
[         console] 2023/08/01 16:11:47 Created new console...
[         console] 2023/08/01 16:11:47 [mbw] RegisterOrganization &{Orderer 0xc0000c7080 0xc00056c390 <nil> OrdererMSP}
[         console] 2023/08/01 16:11:47 [mbw] RegisterOrganization &{Org1 0xc000132720 0xc000133a10 0xc000300960 Org1MSP}
[       microfabd] 2023/08/01 16:11:47 Created and started console
[       microfabd] 2023/08/01 16:11:47 Creating and starting proxy ...
[       microfabd] 2023/08/01 16:11:47 Created and started proxy
[       microfabd] 2023/08/01 16:11:47 Creating and joining channel channel1 ...
[       microfabd] 2023/08/01 16:11:47 Creating channel channel1 ...
[         orderer] 2023-08-01 16:11:47.773 UTC 000f INFO [comm.grpc.server] 1 -> streaming call completed grpc.service=orderer.AtomicBroadcast grpc.method=Broadcast grpc.request_deadline=2023-08-01T16:12:17.757Z grpc.peer_address=127.0.0.1:55214 grpc.code=OK grpc.call_duration=14.898542ms
[         orderer] 2023-08-01 16:11:47.778 UTC 0010 INFO [blkstorage] newBlockfileMgr -> Getting block information from block storage
[         orderer] 2023-08-01 16:11:47.782 UTC 0011 WARN [orderer.consensus.solo] HandleChain -> Use of the Solo orderer is deprecated and remains only for use in test environments but may be removed in the future.
[         orderer] 2023-08-01 16:11:47.782 UTC 0012 INFO [orderer.commmon.multichannel] newChain -> Created and started new channel channel1
[         orderer] 2023-08-01 16:11:47.786 UTC 0013 INFO [comm.grpc.server] 1 -> streaming call completed grpc.service=orderer.AtomicBroadcast grpc.method=Deliver grpc.request_deadline=2023-08-01T16:12:17.774Z grpc.peer_address=127.0.0.1:55214 grpc.code=OK grpc.call_duration=12.223286ms
[         orderer] 2023-08-01 16:11:47.789 UTC 0014 INFO [comm.grpc.server] 1 -> streaming call completed grpc.service=orderer.AtomicBroadcast grpc.method=Deliver grpc.request_deadline=2023-08-01T16:12:17.788Z grpc.peer_address=127.0.0.1:55214 grpc.code=OK grpc.call_duration=1.165846ms
[         orderer] 2023-08-01 16:11:47.792 UTC 0015 INFO [comm.grpc.server] 1 -> streaming call completed grpc.service=orderer.AtomicBroadcast grpc.method=Deliver grpc.request_deadline=2023-08-01T16:12:17.791Z grpc.peer_address=127.0.0.1:55214 grpc.code=OK grpc.call_duration=819.237µs
[         orderer] 2023-08-01 16:11:47.804 UTC 0016 INFO [comm.grpc.server] 1 -> streaming call completed grpc.service=orderer.AtomicBroadcast grpc.method=Broadcast grpc.request_deadline=2023-08-01T16:12:17.794Z grpc.peer_address=127.0.0.1:55214 grpc.code=OK grpc.call_duration=10.596103ms
[       microfabd] 2023/08/01 16:11:47 Created channel channel1
[       microfabd] 2023/08/01 16:11:47 Joining channel channel1 on peer for endorsing organization Org1 ...
[        org1peer] 2023-08-01 16:11:47.813 UTC 0022 INFO [ledgermgmt] CreateLedger -> Creating ledger [channel1] with genesis block
[        org1peer] 2023-08-01 16:11:47.815 UTC 0023 INFO [blkstorage] newBlockfileMgr -> Getting block information from block storage
[        org1peer] 2023-08-01 16:11:47.835 UTC 0024 INFO [couchdb] createDatabaseIfNotExist -> Created state database channel1_
[        org1peer] 2023-08-01 16:11:47.882 UTC 0025 INFO [couchdb] createDatabaseIfNotExist -> Created state database channel1__lifecycle
[        org1peer] 2023-08-01 16:11:47.954 UTC 0026 INFO [kvledger] commit -> [channel1] Committed block [0] with 1 transaction(s) in 57ms (state_validation=0ms block_and_pvtdata_commit=2ms state_commit=53ms) commitHash=[]
[        org1peer] 2023-08-01 16:11:47.954 UTC 0027 INFO [kvledger] updateLedgerStatus -> Updating ledger [channel1] status to [ACTIVE]
[        org1peer] 2023-08-01 16:11:47.955 UTC 0028 INFO [ledgermgmt] CreateLedger -> Created ledger [channel1] with genesis block
[        org1peer] 2023-08-01 16:11:47.967 UTC 0029 INFO [gossip.gossip] JoinChan -> Joining gossip network of channel channel1 with 1 organizations
[        org1peer] 2023-08-01 16:11:47.967 UTC 002a INFO [gossip.gossip] learnAnchorPeers -> No configured anchor peers of Org1MSP for channel channel1 to learn about
[        org1peer] 2023-08-01 16:11:47.967 UTC 002b INFO [gateway] configUpdate -> Updating orderer config channel=channel1
[        org1peer] 2023-08-01 16:11:47.968 UTC 002c INFO [gossip.state] NewGossipStateProvider -> Updating metadata information for channel channel1, current ledger sequence is at = 0, next expected block is = 1
[        org1peer] 2023-08-01 16:11:47.969 UTC 002d INFO [deliveryClient] StartDeliverForChannel -> This peer will retrieve blocks from ordering service and disseminate to other peers in the organization for channel channel1
[        org1peer] 2023-08-01 16:11:47.969 UTC 002e INFO [endorser] callChaincode -> finished chaincode: cscc duration: 161ms channel= txID=4900f1ce
[        org1peer] 2023-08-01 16:11:47.969 UTC 002f INFO [comm.grpc.server] 1 -> unary call completed grpc.service=protos.Endorser grpc.method=ProcessProposal grpc.request_deadline=2023-08-01T16:12:17.806Z grpc.peer_address=127.0.0.1:54740 grpc.code=OK grpc.call_duration=162.452582ms
[       microfabd] 2023/08/01 16:11:47 Joined channel channel1 on peer for endorsing organization Org1
[       microfabd] 2023/08/01 16:11:47 Created and joined channel channel1
[       microfabd] 2023/08/01 16:11:47 Microfab started in 2220ms
[        org1peer] 2023-08-01 16:11:48.399 UTC 0030 INFO [gossip.privdata] StoreBlock -> Received block [1] from buffer channel=channel1
[        org1peer] 2023-08-01 16:11:48.404 UTC 0031 INFO [gossip.gossip] JoinChan -> Joining gossip network of channel channel1 with 1 organizations
[        org1peer] 2023-08-01 16:11:48.404 UTC 0032 INFO [gossip.gossip] learnAnchorPeers -> Learning about the configured anchor peers of Org1MSP for channel channel1: [{org1peer-api.127-0-0-1.nip.io 8080}]
[        org1peer] 2023-08-01 16:11:48.404 UTC 0033 INFO [gossip.gossip] learnAnchorPeers -> Anchor peer for channel channel1 with same endpoint, skipping connecting to myself
[        org1peer] 2023-08-01 16:11:48.404 UTC 0034 INFO [gateway] configUpdate -> Updating orderer config channel=channel1
[        org1peer] 2023-08-01 16:11:48.404 UTC 0035 INFO [committer.txvalidator] Validate -> [channel1] Validated block [1] in 5ms
[        org1peer] 2023-08-01 16:11:48.431 UTC 0036 INFO [kvledger] commit -> [channel1] Committed block [1] with 1 transaction(s) in 26ms (state_validation=0ms block_and_pvtdata_commit=7ms state_commit=17ms) commitHash=[47dc540c94ceb704a23875c11273e16bb0b8a87aed84de911f2133568115f254]
```

# stop microfab
```
control + c
```
```
sudo docker container prune
```