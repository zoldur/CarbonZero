# CarbonZero
Shell script to install a [CarbonZero Masternode]() on a Linux server running Ubuntu 16.04. Use it on your own risk.
This script will install Carbon Zero version 2.0.0.1
***

## VPS installation
```
wget -N https://raw.githubusercontent.com/zoldur/CarbonZero/master/carbonzero_install.sh
bash carbonzero_install.sh
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:
1. Open the CarbonZero Desktop Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **1000** CZE to **MN1**. You need to send all 1000 coins in one single transaction.
4. Wait for 15 confirmations.
5. Go to **Help -> "Debug Window - Console"**
6. Type the following command: **masternode outputs**
7. Go to  ** Tools -> "Open Masternode Configuration File"
8. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* Output index:  **Second value from Step 6** It can be **0** or **1**
9. Click OK and exit the Wallet.
10. Open CarbonZero Wallet, go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Select your MN and click on **Start Alias**
12. Login to your VPS and check your masternode status by running the following command. If you get **Masternode started successfully**, it means your masternode is active.
```
carbonzero-cli masternode status
```
***

## Usage:
```
carbonzero-cli mnsync status
carbonzero-cli masternode status #This will tell you if the masternode is running
carbonzero-cli getinfo
```
Also, if you want to check/start/stop **CarbonZero**, run one of the following commands as **root**:

```
systemctl status CarbonZero #To check if CarbonZero service is running
systemctl start CarbonZero #To start CarbonZero service
systemctl stop CarbonZero #To stop CarbonZero service
systemctl is-enabled CarbonZero #To check if CarbonZero service is enabled on boot
```
***

## Masternode update:
If you were running  Carbon Zero v2.0.0.0, simply running the installer will update your node to v2.0.0.1.
***

## Donations

Any donation is highly appreciated

**BTC**: 3MQLEcHXVvxpmwbB811qiC1c6g21ZKa7Jh
**ETH**: 0x26B9dDa0616FE0759273D651e77Fe7dd7751E01E
**LTC**: LNZpK4rCd1JVSB3rGKTAnTkudV9So9zexB

