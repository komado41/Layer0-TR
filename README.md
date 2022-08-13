# Layer0-TR
# LayerZero - an Omnichain Interoperability Protocol
# LayerZero - an Omnichain Interoperability Protocol (Omnichain Birlikte Çalışabilirlik Protokolü)

This repository contains the smart contracts for LayerZero Endpoints. For developers looking to build on top of LayerZero please refer to the [docs](https://layerzero.gitbook.io/docs/) 
Bu repo, LayerZero Endpoints için akıllı sözleşmeleri içerir. LayerZero'nun üzerine inşa etmek isteyen geliştiriciler için lütfen şuraya bakın: [docs](https://layerzero.gitbook.io/docs/) 

## Overview
LayerZero is an Omnichain Interoperability Protocol designed for lightweight message passing across chains. LayerZero provides authentic and guaranteed message delivery with configurable trustlessness. The protocol is implemented as a set of gas-efficient, non-upgradable smart contracts.
LayerZero, zincirler arasında hafif ileti aktarımı için tasarlanmış bir Omnichain Birlikte Çalışabilirlik Protokolüdür. LayerZero, yapılandırılabilir güvenilmezlik ile özgün ve garantili mesaj teslimi sağlar. Protokol, gaz açısından verimli, yükseltilemeyen bir dizi akıllı sözleşme olarak uygulanmaktadır.

## Development
### Interfaces
add this to your package.json
## Development (Gelişim)
### Interfaces (Arayüzler)
bunu ekleyin package.json

`
    "@layerzerolabs/contracts": "latest",
`
### Setup
### Setup (kurulum)
- copy .env.example to .env and fill in variables
- `yarn install`
### Testing
`yarn test`
#### Single Test File
#### Single Test File (Tek Test Dosyası)
`yarn test test/Endpoint.test.js`
### Gas Uasge
### Gas Uasge (Gaz Kullanımı)
`yarn test:gas`
### Coverage
`yarn test:coverage`
@@ -32,29 +32,31 @@ only lints .js/.ts files

Deploy networks are generated based on tags.

Dağıtım ağları, etiketlere göre oluşturulur.

#### Hardhat
`yarn dev`

spins up local environment and deploys contracts 
local ortamı harekete geçirir ve sözleşmeleri devreye

#### Development
```
hardhat --network rinkeby-testnet deploy
hardhat --network rinkeby-sandbox deploy
```

#### Production
#### Production (üretim)
```
hardhat --network ethereum deploy
```

### Adding a new network
1. Update [hardhat config](hardhat.config.ts) with network
   1. refer to [STAGING_MAP](utils/deploy.js) for staging environments supported 
2. Update [endpoints.json](constants/endpoints.json) with network
3. Make sure that key in endpoints.json matches network name in hardhat
### Adding a new network (Yeni bir ağ ekleme)
1. Güncelleme [hardhat config](hardhat.config.ts) ağ ile
   1. başvurun [STAGING_MAP](utils/deploy.js) desteklenen hazırlama ortamları için 
2. Güncelleme [endpoints.json](constants/endpoints.json) with network
3. endpoints.json'daki anahtarın hardhat'taki ağ adıyla eşleştiğinden emin olun

Example: One LayerZero Network
Example: One LayerZero Network (Örnek: Tek Katmanlı Sıfır Ağ)
```
//hardhat.config.ts
ethereum: {
@@ -71,7 +73,7 @@ ethereum: {
}
```

Example: More than one LayerZero Network on same chain (using expandNetwork)
Örnek: Aynı zincir üzerinde birden fazla LayerZero Ağı (using expandNetwork)
```
//hardhat.config.ts
...expandNetwork({
@@ -89,10 +91,9 @@ Example: More than one LayerZero Network on same chain (using expandNetwork)
   }
}
```
