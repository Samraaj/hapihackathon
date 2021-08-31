---


---

<h1 id="hapi---please-hack-us">Hapi - Please Hack Us!</h1>
<p>Hapi Finance is a new project by <a href="https://twitter.com/sathaxe">@sathaxe</a> and <a href="https://twitter.com/TheBathman_">@TheBathman_</a>. We’re in the early days of building estate management for ethereum wallets. Have you ever wondered what would happen to all of your tokens and NFTs if you died? We want to make sure your loved ones inherit your assets in this sad turn of events!</p>
<p>We’re providing this early look at our smart contracts so that you can try and poke holes in them and provide feedback.</p>
<p>If you didn’t know, <a href="https://en.wikipedia.org/wiki/Hapi_%28Son_of_Horus%29">Hapi</a> is one of the four sons of the Egyptian god Osiris tasked with helping protect the deceased. Hapi is typically depicted on a <a href="https://upload.wikimedia.org/wikipedia/commons/thumb/8/80/Egyptian_-_A_Complete_Set_of_Canopic_Jars_-_Walters_41171,_41172,_41173,_41174_-_Group.jpg/1280px-Egyptian_-_A_Complete_Set_of_Canopic_Jars_-_Walters_41171,_41172,_41173,_41174_-_Group.jpg">Canopic jar</a>, so we decided to hide some digital jars in a couple of the estates in the deployed Will contract. So if you take ownership of them or find any other significant exploits, rest assured we will reward you with a piece of Hapi history - an NFT commissioned by an artist that won’t be available anywhere else!</p>
<h2 id="the-current-environment">The current environment</h2>
<ol>
<li>Everything has been deployed on the Rinkeby testnet.</li>
<li>We have deployed Will.sol at <em>insert address</em></li>
<li>We have initialized multiple estate holders.</li>
</ol>
<h2 id="how-we-set-things-up--how-you-would-deploy-your-own-will-optional">How we set things up / how you would deploy your own will (optional)</h2>
<ol>
<li>
<p>Deploy a Will contract</p>
</li>
<li>
<p>A wallet must call initialize to become an estate holder in the contract<br>
<code>&lt;Will&gt;.initialize(&lt;address of beneficiary&gt;, &lt;checkin cadence&gt;)</code></p>
</li>
<li>
<p>An estate holder approve the will contract from any tokens they want to be transferred<br>
<code>&lt;Token&gt;.approve(&lt;address of will&gt;, &lt;amount of tokens&gt;)</code></p>
</li>
<li>
<p>An estate holder (or anyone else) has to add these tokens to the list of the will’s supported tokens <code>&lt;Will&gt;.addSupportedToken(&lt;address of token&gt;)</code></p>
</li>
<li>
<p>Anyone can call <code>transferIfDead(&lt;address of estate holder&gt;)</code>. If the time between now and the specified user’s last checkin is longer than their cadence the funds will be transferred to their beneficiaries, if not they won’t.</p>
</li>
</ol>
<h2 id="some-tips-on-getting-started">Some tips on getting started</h2>
<ol>
<li>
<p>The code for Will.sol is well documented and verified on Etherscan, so you can poke around with their GUI or load it into Remix.</p>
</li>
<li>
<p>We have deployed three generic ERC20 tokens that anyone can mint up to 1/1000 of the supply for themselves for testing just to speed things up for you. These tokens have already been added to list of supported tokens on the Will we deployed but you will still have to approve that Will to spend your tokens individually.</p>
</li>
<li>
<p>The hidden treasure we mentioned earlier is an ERC20 token and is deployed at <em>insert address</em></p>
</li>
</ol>
<h2 id="some-ideas-for-attacks">Some ideas for attacks</h2>
<ol>
<li>
<p>Since anyone can add an address to the supported tokens list maybe you could create a malicious contract that will be accessed every time someone checks for death</p>
</li>
<li>
<p>Anyone can attempt to start a transfer if dead, this only works if the user is dead, but maybe there’s an exploit there?</p>
</li>
</ol>
<h2 id="submissions">Submissions</h2>
<ol>
<li>Please follow and DM <em>Hapi Twitter account</em> with any exploits you have found.</li>
<li>We will</li>
</ol>

