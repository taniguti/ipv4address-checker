# ipv4address-checker

[シェルスクリプトで IPアドレス計算](https://qiita.com/harasou/items/5c14c335388f70e178f5) を参考に作った、IPv4アドレスをハンドリングするツール集。

## ip2dec
```
./ip2dec 192.168.54.56
3232249400
```

## dec2ip
```
./dec2ip 3232249403
192.168.54.59
```

## cidr2netmask
```
./cidr2netmask 18
255.255.192.0
```

## withinchk
```
./withinchk -i 192.168.54.56 -r 192.168.54.0/20
192.168.54.56 is in 192.168.48.0/255.255.240.0 (STDERR)
return code is 0

./withinchk -i 192.168.54.56 -r 192.168.54.54/255.255.255.248
192.168.54.56 is not in 192.168.54.48/255.255.255.248 (STDERR)
return code is 1

./withinchk -i 192.168.54.56 -r 192.168.54.56
192.168.54.56 is in 192.168.54.56/255.255.255.255 (STDERR)
return code is 0
```

## getnetworkrange
```
./getnetworkrange 192.168.54.20/29
192.168.54.16 192.168.54.23 255.255.255.248

./getnetworkrange 192.168.54.20/255.255.255.128
192.168.54.0 192.168.54.127 255.255.255.128
```
