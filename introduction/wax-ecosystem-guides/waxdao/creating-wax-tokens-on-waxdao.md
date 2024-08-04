# Creating Wax tokens on WaxDAO

WaxDAO has a brilliant tool available for projects/creators to help them create their own secondary tokens on the Wax network, without the need of installing or compiling anything.

{% embed url="https://waxdao.io/token-creator" %}
[https://waxdao.io/token-creator](https://waxdao.io/token-creator)
{% endembed %}

Watch the YouTube tutorial for how it all works here before you get started:

{% embed url="https://youtu.be/qwdumwxJNxg" %}

* The first thing you need to do is to unlock the tool by getting [whitelisted](whitelisting-options.md)
* Then you can deploying the contract via your account (if you have enough CPU/NET/RAM to do so)
  * Your Wax account will need at least 500kb of RAM, 2ms of CPU and 50wax worth of NET, to deploy the contract

<div>

<figure><img src="../../../.gitbook/assets/image (9) (1).png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../../.gitbook/assets/image (10) (1).png" alt=""><figcaption></figcaption></figure>

</div>

* Once you have confirmed on your token contract deploy via your [TX history on Waxblock](../waxblock.io/tx-history-on-waxblock.io.md)
* With the contract deployed, you're now ready to create your token from the "Manage Tokens" toolbox on WaxDAO using the "Create" page:
  * You need to fill in a max supply, a token symbol, and a precision (enabling the token to be splitable into 0-8 decimals)

<div>

<figure><img src="../../../.gitbook/assets/image (11) (1).png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../../.gitbook/assets/image (12) (1).png" alt=""><figcaption></figcaption></figure>

</div>

* When you have your new token created on the blockchain you can switch over to the "Issue" page, from where you can define a number of tokens to issue (they are issued to your token creator wallet)

And your new custom Wax token has now been created on the blockchain, and begun to be issued to your wallet!

{% hint style="info" %}
You can access WaxDAO and the token creator via testnet on https://testnet.waxdao.io/token-creator and try it out safely, before you go live on mainnet.
{% endhint %}

{% hint style="warning" %}
Make sure your account (and it's available wallet resources) live up to the requirements/needs of the token contract to be submitted to the blockchain network.



You need (at time of writing):

* \+50 Wax staked to NET
* \+200 Wax staked to CPU
* \+500 kb available RAM to be spent on the contract (\~250 Wax worth of RAM)
{% endhint %}

If you run into problems along the way reach out to WaxDAO directly via their telegram:

{% embed url="https://t.me/HoodPunks" %}
[https://t.me/HoodPunks](https://t.me/HoodPunks)
{% endembed %}
