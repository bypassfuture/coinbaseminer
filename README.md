coinbaseminer
=============

 curl -l https://raw.githubusercontent.com/blockchain/Blockchain-Known-Pools/master/pools.json |sed 'N;s/{\n//'| grep $(./bitcoind getbestblockhash | xargs -i ./bitcoind  getblock  {} | sed -n '/"tx"/{n;s/"\|,//g;p}' | xargs -i ./bitcoind getrawtransaction {} | xargs -i ./bitcoind decoderawtransaction {} | sed -n '/"addresses"/{n;s/"\|,//g;p}' )
  
            "1CjPR7Z5ZSyWk6WtXvSFgkptmpoi4UM9BC" :                 "name" : "GHash.IO",
