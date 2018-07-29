# customtokens

Custom Token tracking smart contract for Enumivo

# Usage

### View the table

`enucli get table customtokens customtokens tokens`

### Add to the table

```
enucli push action customtokens set '[unique_id, your_account, contract_account, asset_string]' -p your_account@active
```

**Parameter List**:

- **Unique ID**: `1` below, this must be a unique number in the table.
- **Record Owner**: `customtokens` below, the account that manages this table record.
- **Contract Account**: `alwaysliquid` below, the account which holds the smart contract for the token.
- **Asset**: `0.0000 ENU` below, must be `0` and have the correct amount of decimal places (`.0000`), with the correct symbol (`ENU`).

**Example**:

```
enucli push action customtokens set '[1, "customtokens", "alwaysliquid", "0.0000 ENU"]' -p customtokens@active
```

### Remove from the table

```
enucli push action customtokens del '[unique_id]' -p your_account@active
```

**Parameter List**:

- **Unique ID**: `1` below, the unique ID of the row to remove.

**Example**:

`enucli push action customtokens del '[1]' -p customtokens@active`

# How to build

`enumivocpp -g customtokens.abi customtokens.cpp && enumivocpp -o customtokens.wast customtokens.cpp`

# How to deploy

`enucli set contract customtokens customtokens -p customtokens@active`
