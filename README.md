# Hapi - Please Hack Us!
Hapi Finance is a new project by [@sathaxe](https://twitter.com/sathaxe) and [@TheBathman_](https://twitter.com/TheBathman_). We’re in the early days of building estate management for ethereum wallets. Have you ever wondered what would happen to all of your tokens and NFTs if you died? We want to make sure your loved ones inherit your assets in this sad turn of events!

We’re providing this early look at our smart contracts so that you can try and poke holes in them and provide feedback.

If you didn’t know, [Hapi](https://en.wikipedia.org/wiki/Hapi_%28Son_of_Horus%29) is one of the four sons of the Egyptian god Osiris tasked with helping protect the deceased. Hapi is typically depicted on a [Canopic jar](https://upload.wikimedia.org/wikipedia/commons/thumb/8/80/Egyptian_-_A_Complete_Set_of_Canopic_Jars_-_Walters_41171,_41172,_41173,_41174_-_Group.jpg/1280px-Egyptian_-_A_Complete_Set_of_Canopic_Jars_-_Walters_41171,_41172,_41173,_41174_-_Group.jpg), so we decided to hide some digital jars in a couple of the estates in the deployed Will contract. So if you take ownership of them or find any other significant exploits, rest assured we will reward you with a piece of Hapi history - an NFT commissioned by an artist that won’t be available anywhere else!

## The current environment
1.  Everything has been deployed on the Rinkeby testnet.
2.  We have deployed Will.sol at *insert address*
3.  We have initialized multiple estate holders.
## How we set things up / how you would deploy your own will (optional)

1.  Deploy a Will contract
    
2.  A wallet must call initialize to become an estate holder in the contract
`<Will>.initialize(<address of beneficiary>, <checkin cadence>)`
    
4.  An estate holder approve the will contract from any tokens they want to be transferred
 `<Token>.approve(<address of will>, <amount of tokens>)`
    
5.  An estate holder (or anyone else) has to add these tokens to the list of the will's supported tokens `<Will>.addSupportedToken(<address of token>)`
    
6.  Anyone can call `transferIfDead(<address of estate holder>)`. If the time between now and the specified user’s last checkin is longer than their cadence the funds will be transferred to their beneficiaries, if not they won’t.
    

## Some tips on getting started

1.  The code for Will.sol is well documented and verified on Etherscan, so you can poke around with their GUI or load it into Remix.
    
2.  We have deployed three generic ERC20 tokens that anyone can mint up to 1/1000 of the supply for themselves for testing just to speed things up for you. These tokens have already been added to list of supported tokens on the Will we deployed but you will still have to approve that Will to spend your tokens individually.
    
3.  The hidden treasure we mentioned earlier is an ERC20 token and is deployed at *insert address*
    

## Some ideas for attacks

1.  Since anyone can add an address to the supported tokens list maybe you could create a malicious contract that will be accessed every time someone checks for death
    
2.  Anyone can attempt to start a transfer if dead, this only works if the user is dead, but maybe there’s an exploit there?

## Submissions

1. Please follow and DM *Hapi Twitter account* with any exploits you have found.
2. We will 





