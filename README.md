# mn-setup
# MasternodeSetup

### Required:

1. SMNC Coin for Collateral <br>
(You can buy SMNC from exchange for collateral) <br>
*** <br>
Exchange: https://graviex.net/markets/smncbtc
<br>***

2. Download your Local Wallet: https://github.com/smnccoin/smnc/releases/download/v1000/SMNC-Win-1000-Wallet.zip

- You can see daily income and collateral info here: 


3. You will need also VPS with Ubuntu 16.04 or 18.04

**VPS WALLET:**

1. After you longin on your VPS , with this command you will download masternode-installer.   
`wget https://raw.githubusercontent.com/smnccoin/mn-setup/main/masternode-install-ubuntu.sh`  
 

2. With this command you will make masternode-install-ubuntu.sh executable.  
`sudo chmod +x masternode-install-ubuntu.sh` <br>



3. Now install your masternode.  
`./masternode-install-ubuntu.sh`




**LOCAL WALLET:**

Send the collateral
Open your wallet and wait until your wallet has downloaded the blockchain.

Go to “Tools”.
Click “Debug console”.
This is the console where you will execute all commands.

Create a new masternode private key.

```
createmasternodekey
```

Example output

7VatfYVk5fFMTymPDhgSURAESDACJhWpd89WHGoh35d9fbLQPj5

Show your collateral address.
```
getaccountaddress "MN01"
```

Example output

ShCQLnPeH2Z7FoKfvn7VDwJ8jBmhnq2vVZ
```
Transfer the required amount of coins to the “collateral address” that you created using the command “getaccountaddress "MN1"”.
```
Wait until the transaction has the required masternode confirmations.

Go to “Tools”.
Click “Debug console”.
Enter the following command.
```
getmasternodeoutputs
```
```
Example output


[
  {
    "txhash": "3dsa242ccbfd2555bcd9cff4532041752c911f39cb2sawgacc83ccfe0cf8808fsw",
    "outputidx": 1
  }
]
```

Modify the following line in your masternode.conf file and paste it into:
```
MN01 VPSIP:39454 7VatfYVk5fFMTymPDhgSURAESDACJhWpd89WHGoh35d9fbLQPj5 506a242ccbfd2555bcd9cff5f4041752c911f39cb2905acc83ccfe0cf8808df9 1
```
MN01 - Alias for your masternode.

VPSIP- External IP address of your VPS.

39454 - The port for smnc 

7VatfYVk5fFMTymPDhgSURAESDACJhWpd89WHGoh35d9fbLQPj5 - Masternode private key from the command “createmasternodekey”.

506a242ccbfd2555bcd9cff5f4041752c911f39cb2905acc83ccfe0cf8808df9 - Value “txhash” from the command “getmasternodeoutputs”.

1 - Value “outputidx” from the command “getmasternodeoutputs”.


Save the file and close.

Close your wallet.

Restart your wallet! 
On Masternode tab in your wallet - Start the masternode!
