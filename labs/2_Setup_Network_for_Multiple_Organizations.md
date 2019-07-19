Setup a new channel with multiple members

1.  Remove (or move) the crypto-config directory (simple-two-org directory from the cryptogen directory)

rm -rf ~/HLF*/cryptogen/crypto-config 2>/dev/null

2.  Copy the crypto-config.yaml from .../setup/config/simple-two-org/crypto.2 to ~/HLF*/cryptogen/simple-two-org/

3.  Copy the crypto-configtx.yaml from .../setup/config/simple-two-org/policy.1 to ~/HLF*/configtx/simple-two-org/

**Note - you will be editing configtx.yaml BUT remember that there are two parts to this (and all net new adds)... 
first, you must generate the crypto material.  Second, update the configtx.yaml with a profile to create a new channel.

Name the channel whatever you like and make sure to add both Orgs to the channel

4.  Generate the crypto material (reference last lab)

5.  Go into configtx/simple-two-org and create or modify configtx.yaml to create a channel with the multiple organizations so that you generate

(SAMPLE VALUES SUBMITTED BELOw - REFERENCE YOUR yaml FILE FOR ACTUAL VALUES)
`- genesis.block
configtxgen -outputBlock ./my-genesis.block -profile MyProfile -channelID myordererchannel
configtxgen -inspectBlock ./my-genesis.block
- channel.tx
configtxgen -outputCreateChannelTx my-channel.tx -profile MyProfile -channelID myordererchannel
configtxgen -inspectChannelCreateTx my-channel.tx
- org1Anchor.tx
configtxgen -outputAnchorPeersUpdate Org1Anchors.tx -profile MyProfile -channelID myordererchannel -asOrg Org1
configtxgen -printOrg Org1 > Org1.json
`

