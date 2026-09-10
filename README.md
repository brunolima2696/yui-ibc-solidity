<div align="center">
  <h1>ibc-solidity</h1>
</div>

> Fork de [hyperledger-labs/yui-ibc-solidity](https://github.com/hyperledger-labs/yui-ibc-solidity), mantido para suportar a interoperabilidade ICS-20 com chains baseadas em versões recentes do `ibc-go`.

![banner](docs/img/IBC-solidity-cover.svg)

<div align="center">
  <img alt="Version" src="https://img.shields.io/github/tag/hyperledger-labs/yui-ibc-solidity.svg">
  <a href="https://github.com/hyperledger-labs/yui-ibc-solidity/blob/main/LICENSE">
    <img alt="License: Apache-2.0" src="https://img.shields.io/github/license/hyperledger-labs/yui-ibc-solidity.svg" />
  </a>
  <a href="https://github.com/hyperledger-labs/yui-ibc-solidity/actions/workflows/test.yml">
    <img alt="Test" src="https://github.com/hyperledger-labs/yui-ibc-solidity/actions/workflows/test.yml/badge.svg" />
  </a>
  <a href="https://pkg.go.dev/github.com/hyperledger-labs/yui-ibc-solidity?tab=doc">
    <img alt="GoDoc" src="https://godoc.org/github.com/hyperledger-labs/yui-ibc-solidity?status.svg" />
  </a>
</div>

[IBC](https://github.com/cosmos/ibc) implementations in Solidity.

**IBC compatibility:** [v8](https://github.com/cosmos/ibc-go/releases/tag/v8.2.0)


## Alterações deste fork

O parser de pacotes ICS-20 passou a aceitar também a serialização JSON utilizada pelo `ibc-go` v10, cuja ordem de campos é:

```json
{"denom":"...","amount":"...","sender":"...","receiver":"..."}
```

O campo opcional `memo` também é suportado. O formato legado, iniciado por `amount`, permanece compatível.

A alteração foi validada por testes unitários do parser e por transferências IBC bidirecionais entre uma XRPL EVM baseada em `ibc-go` v10 e uma chain Indy-Besu, incluindo o recebimento dos pacotes e seus acknowledgements.

