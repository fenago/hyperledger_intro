In this exercise you will learn how to setup the cryptogen config yaml file

1.  Take the existing crypto-config.yaml file (~/HLF*/cryptogen/simple-two-org) and copy it (name it new-crypto-config.yaml) and then extend it to create the crypto for a new Organization.  Name the organization something unique (Not budget.com).  Use the existing Org as a template.

2.  Generate the crypto material by calling:

cryptogen generate --help     #to get the syntax

cryptogen generate --config ./new-crypto-config.yaml

3. Validate that the crypto material was created for the organizations by going into the generated crypto-config DIRECTORY and then navigate to peerOrganizations.  Explore the various directories

4.  Extend your organization by adding a new peer.  Do this by creating a NEW yaml file with ony the new peer information that you are adding.  

# Extends the crypto material for the setup
# Adds a new peer for Org1

#### Peers for acme
PeerOrgs:
  # Peer configuration for ACME
  - Name: Org1
    Domain: acme.com
    Specs:
      - Hostname: devpeer2
        CommonName: devpeer2
        
5.  Create the crypto for the new peer with:

cryptogen extend --help

cryptogen extend --config ./extend-crypto-config.yaml     (or whatever you named your file)


<!-- Docs to Markdown version 1.0β17 -->
