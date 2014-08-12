coinbaseminer
=============

root@li596-166:~/bitcoin/src#  curl -l https://raw.githubusercontent.com/blockchain/Blockchain-Known-Pools/master/pools.json |sed 'N;s/{\n//'| grep $(./bitcoind getbestblockhash | xargs -i ./bitcoind  getblock  {} | sed -n '/"tx"/{n;s/"\|,//g;p}' | xargs -i ./bitcoind getrawtransaction {} | xargs -i ./bitcoind decoderawtransaction {} | sed -n '/"addresses"/{n;s/"\|,//g;p}' )

  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  7276  100  7276    0     0   175k      0 --:--:-- --:--:-- --:--:--  373k
            "1CjPR7Z5ZSyWk6WtXvSFgkptmpoi4UM9BC" :                 "name" : "GHash.IO",

root@li596-166:~/bitcoin/src# bash -version
GNU bash, version 4.2.25(1)-release (x86_64-pc-linux-gnu)
Copyright (C) 2011 Free Software Foundation, Inc.
