# Sending Transactions

## Action Enum

<table><thead><tr><th width="340">enum</th><th>chain used</th></tr></thead><tbody><tr><td><code>withdraw</code></td><td>EVM, ripple, celestia</td></tr><tr><td><code>contract-interaction</code></td><td>EVM</td></tr><tr><td><code>trust-set</code></td><td>ripple</td></tr><tr><td><code>trust-set-removal</code></td><td>ripple</td></tr><tr><td><code>stake</code></td><td>celestia</td></tr><tr><td><code>unstake</code></td><td>celestia</td></tr><tr><td><code>restake</code></td><td>celestia</td></tr><tr><td><code>reward</code></td><td>celestia</td></tr><tr><td><code>vote</code></td><td>celestia</td></tr></tbody></table>



## Chain Specific Object Examples

### EVM Legacy (type-0) transactions

`type` must be set as `0`. \
Please use EIP-1559 gas params if your chain is supported.

_note: BSC only_

#### `withdraw`

```json
{
    "type": "0",
    "gasLimit": "0x285c6",
    "maxPrice": "0x6ddb024c",
}
```

#### `contract-interaction`

```json
{
    "data": "0x3593564c0000000...",
    "type": "0",
    "value": "0x39696f3392000",
    "gasLimit": "0x285c6",
    "maxPrice": "0x6ddb024c",
}
```



### EVM EIP-1559 (type-2) transactions

`type` must be set as `2`.

#### `withdraw`

```json
{
    "type": "2",
    "gasLimit": "0x285c6",
    "maxFeePerGas": "0x6ddb024c",
    "maxPriorityFeePerGas": "0x59682f00"
}
```

#### `contract-interaction`

```json
{
    "data": "0x3593564c0000000...",
    "type": "2",
    "value": "0x39696f3392000",
    "gasLimit": "0x285c6",
    "maxFeePerGas": "0x6ddb024c",
    "maxPriorityFeePerGas": "0x59682f00"
}
```



### Ripple

#### `withdraw`

<pre class="language-json"><code class="lang-json"><strong>{
</strong>  "Fee": "12",
}
</code></pre>

#### `trust-set`

However, `flags` are required when action is `trust-set`.&#x20;

<table><thead><tr><th width="214">flag</th><th>description</th></tr></thead><tbody><tr><td><code>auth</code></td><td>Authorize the other party to hold currency issued by this account.</td></tr><tr><td><code>freeze</code></td><td>Freeze this trust line.</td></tr><tr><td><code>noRipple</code></td><td>blocks rippling between two trust lines of the same currency if this flag is enabled on both.</td></tr></tbody></table>

<pre class="language-json"><code class="lang-json">{
  "Fee": "12",
  "flags": {
    "auth": true,
    "freeze": false,
    "noRipple": false
  }
<strong>}
</strong></code></pre>

#### `trust-set-removal`

```json
{
  "Fee": "12",
}
```

### Celestia

#### `withdraw`

```json
{
    "denom": "utia",
    "gasPrice": "0.04",
    "gasLimit": "500000",
}
```

#### `stake`

<pre class="language-json"><code class="lang-json"><strong>{
</strong>    "memo": "staking testing",
    "denom": "utia",
    "gasPrice": "0.04",
    "gasLimit": "500000",
}
</code></pre>

#### `unstake`

```json
{
    "memo": "unstaking testing",
    "denom": "utia",
    "gasPrice": "0.04",
    "gasLimit": "500000",
}
```

#### `restake`

```json
{
    "denom": "utia",
    "gasPrice": "0.04",
    "gasLimit": "500000"
}
```

#### `reward`

```json
{
    "denom": "utia",
    "gasPrice": "0.04",
    "gasLimit": "500000"
}
```

#### `vote`

```json
{
    "memo": "voting testing",
    "denom": "utia",
    "gasPrice": "0.04",
    "gasLimit": "500000",
    "voteOption": "yes",
    "proposalId": "819"
}
```
