Makes use of [[Public & Secret Key]], [[User Keychain]], [[State Synchronization]].

Having a device constellation is important for several reasons:

1. I want data to synchronize between my devices.
2. If I lose access to a device, I want to continue accessing my account through my remaining devices.
3. I need procedures for restoring access to my account which may involve secondary devices or use of a paper backup key.

Consider the identity recovery services that a bank provides for their customers.  If I lose my debit card or forget my pin number, I can go down to the bank and request that they restore my access.  They will take steps to verify my identity and then comply with my request.

In the cryptography world, losing your keys means you no longer have access to your money, your data, or any of the devices that were secured through those keys.  For many people, forgetting a password or damaging a device is a more likely scenario than theft.  We need a solution similar to what banks provide, which allows recovery from an accident with minimal pain, while still giving options should theft of a device occur.  If all devices are stolen simultaneously, then a paper key serves as a final option, to revoke permissions on all devices and hopefully minimize transfer of cryptocurrency and other ledger based assets.

In order for a system like this to work, users need to be educated on the responsibilities of owning their own keys.

The alternative is a custodial arrangement such as [coinbase](https://www.coinbase.com/) which manages your keys for you.  Even though this may use the technology of a SSID, the end result is that you have delegated your sovereignty.  This has consequences:

1. If that central repository gets hacked, all of the identities within it may be compromised.  Will insurance cover your loss?
2. If the central repository decides that you have violated a policy, they may lock you out from accessing your resources and/or identity.
3. If requested by government authorities they may hand over your assets and/or freeze your accounts.

For these reasons, a person valuing autonomy should take responsibility for their own key management, and should educate themselves on proper stewardship of such keys.

##### Implementations

SSID was implemented by [Keybase](https://keybase.io/).  Their workflow involved scanning a QR code on new devices, and was approachable for non-technical users.  Unfortunately Keybase was [bought by Zoom](https://decrypt.co/28121/keybase-users-revolt-following-zoom-acquisition), and their product team was reassigned to "making Zoom more secure".

Holochain has an effort called [DeepKey](https://github.com/holochain/deepkey) to implement SSID.  [Will it come to completion](https://forum.holochain.org/t/deepkey-status/6969/10)?

