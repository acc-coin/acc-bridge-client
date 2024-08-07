# ACC Bridge Validator

-----

## Docker Engine 설치
Bridge Client 를 실행하기 위해서는 먼저 도커엔진을 설치하여야 합니다.  
도커엔진을 설치하기 위해서는 [여기](https://docs.docker.com/engine/install/)를 참조하십시오  
https://docs.docker.com/engine/install/


## Bridge Client 설치
```shell
git clone https://github.com/acc-coin/acc-bridge-validator.git
cd acc-bridge-validator
```
---

## 테스트넷에서 실행하기


### 준비
1. 검증자키 생성  
사용하고 계신 메타마스크의 비밀키를 사용하면 됩니다.  
2. 검증자키 등록  
지갑의 비밀키를 testnet/.chain-bridge.env 와 testnet/.loyalty-bridge.env 에 등록합니다.  

testnet/.chain-bridge.env  
```toml
# ...
# A: MainChain
# B: SideChain
A_BRIDGE_CONTRACT_ADDRESS = 0x097C7543464d3De422f86248F1CE803879a4077e
B_BRIDGE_CONTRACT_ADDRESS=0x2902aa3D47075AB2b87e8345094Ea1c87e5B5019
A_TOKEN_CONTRACT_ADDRESS = 0xBd837b831cA3aA1e9eE388959d9f5B81262ccfA6
B_TOKEN_CONTRACT_ADDRESS=0x8D34D6102AD64abDa8bcF36c278140bAC4D97323

BRIDGE_VALIDATOR_KEY = 0x00 # 여기에 등록합니다. 0x로 시작되는 16진 문자열입니다. 전체 66개 문자입니다

```
testnet/.loyalty-bridge.env
```toml
# ...
# A: MainChain
# B: SideChain
A_BRIDGE_CONTRACT_ADDRESS = 0x22B98e18c51D02AF225b3fBa726865fB497B1afD
B_BRIDGE_CONTRACT_ADDRESS = 0x877ab4A2d858926EE65769723d4ea825E055024e
A_TOKEN_CONTRACT_ADDRESS = 0xBd837b831cA3aA1e9eE388959d9f5B81262ccfA6
B_TOKEN_CONTRACT_ADDRESS=0x8D34D6102AD64abDa8bcF36c278140bAC4D97323

BRIDGE_VALIDATOR_KEY = 0x00 # 여기에 등록합니다. 0x로 시작되는 16진 문자열입니다. 전체 66개 문자입니다

```

### 실행

```shell
cd testnet
docker compose up -d
```

### 종료

```shell
cd testnet
docker down
```

----

## 메인넷에서 실행하기


### 준비
1. 검증자키 생성  
   사용하고 계신 메타마스크의 비밀키를 사용하면 됩니다.
2. 검증자키 등록  
   지갑의 비밀키를 mainnet/.chain-bridge.env 와 mainnet/.loyalty-bridge.env 에 등록합니다.

mainnet/.chain-bridge.env
```toml
# ...
# A: MainChain
# B: SideChain
A_BRIDGE_CONTRACT_ADDRESS = 0xf0ecB578ACd2FABfE138b7b93bd558a7Cb42450f
B_BRIDGE_CONTRACT_ADDRESS = 0xcCE559B92B82Fdc8302617D49AacF30AdBC50492
A_TOKEN_CONTRACT_ADDRESS = 0xB5e4d7AF952F612A2CCB1474b49bd03459F1429f
B_TOKEN_CONTRACT_ADDRESS = 0xB5e4d7AF952F612A2CCB1474b49bd03459F1429f

BRIDGE_VALIDATOR_KEY = 0x00 # 여기에 등록합니다. 0x로 시작되는 16진 문자열입니다. 전체 66개 문자입니다

```
mainnet/.loyalty-bridge.env
```toml
# ...
# A: MainChain
# B: SideChain
A_BRIDGE_CONTRACT_ADDRESS = 0x58B6136d7A84E60C869fBf7465FF3Dc1BdF461c5
B_BRIDGE_CONTRACT_ADDRESS = 0xE939AA8690B68653e7e51a0955EF7d9aCc0AE9D4
A_TOKEN_CONTRACT_ADDRESS = 0xB5e4d7AF952F612A2CCB1474b49bd03459F1429f
B_TOKEN_CONTRACT_ADDRESS = 0xB5e4d7AF952F612A2CCB1474b49bd03459F1429f

BRIDGE_VALIDATOR_KEY = 0x00 # 여기에 등록합니다. 0x로 시작되는 16진 문자열입니다. 전체 66개 문자입니다

```

### 실행

```shell
cd mainnet
docker compose up -d
```

### 종료

```shell
cd mainnet
docker down
```
