# LucidOcean.MultiChain Assembly

The library is an unofficial wrapper for multichain_cli JSON RPC. 
Refer to https://www.multichain.com/developers/json-rpc-api/ for more information on each JSON RPC call and how it is used.

Follow these instructions to create your own chain. https://www.multichain.com/developers/creating-connecting/


This library divides the calls into 
 - MultiChainClient.Address
 - MultiChainClient.Asset
 - MultiChainClient.Block
 - MultiChainClient.Peer
 - MultiChainClient.Permission
 - MultiChainClient.Transaction
 - MultiChainClient.Utility
 - MultiChainClient.Wallet
 - MultiChainClient.Stream

*example usage:*
```csharp
MultiChainConnection connection = new MultiChainConnection()
            {
                Hostname = "IP",
                Port = 100,
                Username = "multichainrpc",
                Password = "password",
                ChainName = "chain1",
                BurnAddress = "address",
                RootNodeAddress = "address"
            };
            
MultiChainClient _Client = new MultiChainClient(connection);
response = _Client.Wallet.GetNewAddress();
```
There are sync and async versions.


##Issue and Send an Asset

```csharp
MultiChainConnection connection = new MultiChainConnection()
            {
                Hostname = "IP",
                Port = 100,
                Username = "multichainrpc",
                Password = "password",
                ChainName = "chain1",
                BurnAddress = "address",
                RootNodeAddress = "address"
            };
            
MultiChainClient _Client = new MultiChainClient(connection);
JsonRpcResponse<string> response = _Client.Asset.Issue(issueAddress, assetName, quantity, units);
_Client.Asset.Send(toAddress, assetName, amount);

//Use SendAssetFrom to specify an address FROM and and address To


```

