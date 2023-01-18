

#   “This page is for special small-scale test purpose and by invitation only. Please do not submit if you are not in this goup of tester. We will refresh the page once we are ready for the mainnet launch."


## Create validator gentx file

uptick version v0.2.4


#### 1、 Initialize the node
```
uptickd init Validator --chain-id=uptick_117-1 
```
#### 2、Create or import Validator wallet

Create：
```
uptickd keys add MyValidator  --keyring-backend=file
```

Import:

```
uptickd keys add MyValidator --recover  --keyring-backend=file
```

#### 3、Add account to ‘genesis’ file

```
uptickd add-genesis-account MyValidator 30000000000000000000000000auptick --keyring-backend=file
```

#### 4、Create a validator transaction. You can customize your node information, including "moniker"、"identity"、"website"、"details"

```
uptickd gentx MyValidator 30000000000000000000000000auptick \
 --chain-id=uptick_117-1\
 --commission-rate="0.10" \
 --commission-max-rate="0.20" \
 --commission-max-change-rate="0.01" \
 --min-self-delegation="1000000" \
 --moniker="moniker" \
 --identity="identity" \
 --website="website" \
 --details="details" \
 --keyring-backend=file
```

#### 5、Submit the gentx file

```
 tar -zcvf  gentx.tar.gz  $HOME/.uptickd/config/gentx
```

Send an email to "validator@uptickproject.com" with the title "Genesis Node Information ｜ <$Validator name>" and the attachment as "gentx.tar.gz"

#### 6、Back up and save the "$HOME/.uptickd/config" file
