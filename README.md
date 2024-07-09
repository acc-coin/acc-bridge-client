# ACC Bridge Client

-----

## Docker Engine 설치
Bridge Client 를 실행하기 위해서는 먼저 도커엔진을 설치하여야 합니다.  
도커엔진을 설치하기 위해서는 [여기](https://docs.docker.com/engine/install/)를 참조하십시오  
https://docs.docker.com/engine/install/


## Bridge Client 설치
```shell
git clone https://github.com/acc-coin/acc-bridge-client.git
cd acc-bridge-client
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
...
# A: MainChain
# B: SideChain
A_BRIDGE_CONTRACT_ADDRESS=0x1756e5c3f6e8039503B711eC8D01223d7e5b0453
B_BRIDGE_CONTRACT_ADDRESS=0x2902aa3D47075AB2b87e8345094Ea1c87e5B5019
A_TOKEN_CONTRACT_ADDRESS=0xf3621dAC696fA3a6F088684c9cdDCe41486213da
B_TOKEN_CONTRACT_ADDRESS=0x8D34D6102AD64abDa8bcF36c278140bAC4D97323

BRIDGE_VALIDATOR_KEY=0x............ // 여기에 등록합니다. 0x로 시작됩니다.

```
testnet/.loyalty-bridge.env
```toml
...
# A: MainChain
# B: SideChain
A_BRIDGE_CONTRACT_ADDRESS=0x1756e5c3f6e8039503B711eC8D01223d7e5b0453
B_BRIDGE_CONTRACT_ADDRESS=0x2902aa3D47075AB2b87e8345094Ea1c87e5B5019
A_TOKEN_CONTRACT_ADDRESS=0xf3621dAC696fA3a6F088684c9cdDCe41486213da
B_TOKEN_CONTRACT_ADDRESS=0x8D34D6102AD64abDa8bcF36c278140bAC4D97323

BRIDGE_VALIDATOR_KEY=0x............ // 여기에 등록합니다. 0x로 시작됩니다.

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
...
# A: MainChain
# B: SideChain
A_BRIDGE_CONTRACT_ADDRESS=0x1756e5c3f6e8039503B711eC8D01223d7e5b0453
B_BRIDGE_CONTRACT_ADDRESS=0x2902aa3D47075AB2b87e8345094Ea1c87e5B5019
A_TOKEN_CONTRACT_ADDRESS=0xf3621dAC696fA3a6F088684c9cdDCe41486213da
B_TOKEN_CONTRACT_ADDRESS=0x8D34D6102AD64abDa8bcF36c278140bAC4D97323

BRIDGE_VALIDATOR_KEY=0x............ // 여기에 등록합니다. 0x로 시작됩니다.

```
mainnet/.loyalty-bridge.env
```toml
...
# A: MainChain
# B: SideChain
A_BRIDGE_CONTRACT_ADDRESS=0x1756e5c3f6e8039503B711eC8D01223d7e5b0453
B_BRIDGE_CONTRACT_ADDRESS=0x2902aa3D47075AB2b87e8345094Ea1c87e5B5019
A_TOKEN_CONTRACT_ADDRESS=0xf3621dAC696fA3a6F088684c9cdDCe41486213da
B_TOKEN_CONTRACT_ADDRESS=0x8D34D6102AD64abDa8bcF36c278140bAC4D97323

BRIDGE_VALIDATOR_KEY=0x............ // 여기에 등록합니다. 0x로 시작됩니다.

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
