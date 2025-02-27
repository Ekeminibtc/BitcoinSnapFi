# BitcoinSnapFi - Photography NFT Platform

## Overview
BitcoinSnapFi is a smart contract built on Stacks blockchain for creating, trading, and managing photography NFTs. This contract enables photographers to mint their photos as NFTs, list them for sale, and earn royalties from secondary sales.

## Features
- **Mint NFTs:** Photographers can tokenize their photos and store metadata.
- **Transfer NFTs:** Owners can transfer NFTs to other users.
- **List NFTs for Sale:** Users can list their NFTs at a set price.
- **Buy NFTs:** Buyers can purchase NFTs, with royalties automatically distributed.
- **Royalty System:** A percentage of sales is sent to the original photographer.
- **View NFT Details:** Anyone can fetch NFT metadata and listings.

## Constants
- `contract-owner` → The contract deployer.
- `err-owner-only` (u100) → Error for unauthorized owner actions.
- `err-not-token-owner` (u101) → Error if the sender does not own the NFT.
- `err-listing-not-found` (u102) → Error if the listing does not exist.
- `err-insufficient-payment` (u103) → Error for insufficient payment.

## Data Structures
### NFT Definition
- **`pixel-photo`** → A non-fungible token representing a photo.

### Mappings
- **photo-metadata** → Stores metadata (photographer, title, timestamp, camera details, location, settings) for each photo.
- **photo-listings** → Stores listing information (price, seller) for each photo.
- **royalty-settings** → Stores royalty percentage and recipient information.

### Data Variables
- **last-token-id** → Tracks the last assigned NFT ID.

## Functions

### Private Functions
- `is-owner(photo-id, user)` → Checks if a given user is the owner of an NFT.

### Public Functions
#### `mint-photo(title, camera-model, location, settings, royalty-percentage) → uint`
Mints a new photo NFT and stores its metadata.

#### `transfer(photo-id, recipient) → bool`
Transfers an NFT from the owner to another user.

#### `list-for-sale(photo-id, price) → bool`
Lists an NFT for sale at a specified price.

#### `buy-photo(photo-id) → bool`
Allows a user to buy an NFT. The payment is transferred to the seller, and a royalty fee is distributed to the original photographer.

### Read-Only Functions
#### `get-photo-details(photo-id) → {photographer, title, timestamp, camera-model, location, settings}`
Returns metadata details for a given NFT.

#### `get-listing(photo-id) → {price, seller}`
Returns listing details for a given NFT.

#### `get-last-token-id() → uint`
Returns the last assigned token ID.

## Deployment & Usage
1. Deploy the contract on the Stacks blockchain.
2. Use the `mint-photo` function to tokenize a photo.
3. Use `list-for-sale` to make the NFT available for purchase.
4. A buyer calls `buy-photo` to purchase the NFT.
5. Use `get-photo-details` and `get-listing` for information retrieval.

## License
MIT License

## Author
Developed for the **BitcoinSnapFi Photography NFT Platform**.

