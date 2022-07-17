# LNURLw_with_LNbits
## Process for use LNURLw with Lnbits

I have use these function in my project 
Bitcoin Quiz 
http://bitcoinquiz.fr/


# LNbits
1. Go on https://www.lnbits.com/
2. Create a new wallet 
3. Go to manage extension
<br></br>
![image](https://user-images.githubusercontent.com/96888096/179379266-d220d698-89a7-40f4-a101-2e2550ded7a0.png)

4. Enable LNURLw
<br></br>
![image](https://user-images.githubusercontent.com/96888096/179379272-04b7cf50-4be2-454d-a48e-f220a80f572f.png) 

<br></br>

# LNURLw
### install lnbits 
``` bash
npm Install lnbits
```

### import LNbits
```
// import LNbits
import LNBits from 'lnbits';
```


### Use Wallet for use default API of LNbits
```
const { wallet } = LNBits({
	adminKey: 'xxxxxx',
	invoiceReadKey: 'xxxxxxx',
	endpoint: 'https://www.lnbits.com', //default
});
```

```
// collect balance of wallet 
const Balance = async () => {
	const walletDetails = await wallet.walletDetails();
	const balanceWallet = walletDetails['balance']
};
```

```
// create an invoice for a user to send satoshi
const createInvoce = async () => {
	const newInvoice = await wallet.createInvoice({
		amount: int //amount that the user will send,
		memo: "str",
		out: false, //sense of transaction
	});
	Req = newInvoice['payment_request']
	Hash = newInvoice['payment_hash']
};
```



### Use withdraw for use LNURLw  
```
const { withdraw } = LNBits({
    adminKey: 'xxxxxxxx',
    invoiceReadKey: 'xxxxxxxxx',
    endpoint: 'https://www.lnbits.com', //default
});
```

```
//Generate Withdraw for receive satoshis
const Withdraw = async () => { {
	const link = await withdraw.createLink({
		title: "str",
		min_withdrawable: int,
		max_withdrawable: int,
		uses: int,
		wait_time: int,
		is_unique: bool,
	});
}
```
