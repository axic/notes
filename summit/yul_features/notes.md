<!--
Solidity is a relatively young language in a rapidly evolving space. The challenges it faces changed over time, greatly influencing the language design. In this brief talk we examine the current language design processes in place and compare it against other models (i.e. language design committees).

the "thoughts on language design" started out as a 5 minute talk arguing why i'm worried about alternative compilers making language changes, but evolved into giving examples how language design works in the team and why is it important to effectively coordinate rapid changes, since it is a young language/space

- Original design space
- Current design space
- Future design space
- Long release cycle: 0.4
- Non-conformant changes: unicode identifiers
- Future: independent design team

Thesis: Solidity needs to evolve rapidly.
-->

---


---

<!--
### 0.6.7 (unreleased)
### 0.6.6 (2020-04-09)
### 0.6.5 (2020-04-06)
### 0.6.4 (2020-03-10)
### 0.6.3 (2020-02-18)
### 0.6.2 (2020-01-27)
### 0.6.1 (2020-01-02)
### 0.6.0 (2019-12-17)
### 0.5.17 (2020-03-17)
### 0.5.16 (2020-01-02)
### 0.5.15 (2019-12-17)
### 0.5.14 (2019-12-09)
### 0.5.13 (2019-11-14)
### 0.5.12 (2019-10-01)
### 0.5.11 (2019-08-12)
### 0.5.10 (2019-06-25)
### 0.5.9 (2019-05-28)
### 0.5.8 (2019-04-30)
### 0.5.7 (2019-03-26)
### 0.5.6 (2019-03-13)
### 0.5.5 (2019-03-05)
### 0.5.4 (2019-02-12)
### 0.5.3 (2019-01-22)
### 0.5.2 (2018-12-19)
### 0.5.1 (2018-12-03)
### 0.5.0 (2018-11-13)
### 0.4.26 (2019-04-29)
### 0.4.25 (2018-09-12)
### 0.4.24 (2018-05-16)
### 0.4.23 (2018-04-19)
### 0.4.22 (2018-04-16)
### 0.4.21 (2018-03-07)
### 0.4.20 (2018-02-14)
### 0.4.19 (2017-11-30)
### 0.4.18 (2017-10-18)
### 0.4.17 (2017-09-21)
### 0.4.16 (2017-08-24)
### 0.4.15 (2017-08-08)
### 0.4.14 (2017-07-31)
### 0.4.13 (2017-07-06)
### 0.4.12 (2017-07-03)
### 0.4.11 (2017-05-03)
### 0.4.10 (2017-03-15)
### 0.4.9 (2017-01-31)
### 0.4.8 (2017-01-13)
### 0.4.7 (2016-12-15)
### 0.4.6 (2016-11-22)
### 0.4.5 (2016-11-21)
### 0.4.4 (2016-10-31)
### 0.4.3 (2016-10-25)
### 0.4.2 (2016-09-17)
### 0.4.1 (2016-09-09)
### 0.4.0 (2016-09-08)
### 0.3.6 (2016-08-10)
### 0.3.5 (2016-06-10)
### 0.3.4 (2016-05-31)
### 0.3.3 (2016-05-27)
### 0.3.2 (2016-04-18)
### 0.3.1 (2016-03-31)
### 0.3.0 (2016-03-11)
### 0.2.2 (2016-02-17)
### 0.2.1 (2016-01-30)
### 0.2.0 (2015-12-02)
### 0.1.7 (2015-11-17)
### 0.1.6 (2015-10-16)
### 0.1.5 (2015-10-07)
### 0.1.4 (2015-09-30)
### 0.1.3 (2015-09-25)
### 0.1.2 (2015-08-20)
### 0.1.1 (2015-08-04)
### 0.1.0 (2015-07-10)
-->

Random facts:
- 0.1.0 -- 2015-07-10
- 0.1.1 -- 2015-08-04 -- the oldest version available in solc-bin
- 0.1.2 -- the oldest version on the release page
- Ethereum Frontier Thawing -- 2015-08-05
- 0.1.6 -- the first version i've used
- 0.2.0 -- the first breaking change
  * **Breaking Change**: `new ContractName.value(10)()` has to be written as `(new ContractName).value(10)()`
- 0.3.0 -- 2016-0-11
- 0.1 series: 7 releases (2015-07-10 -> 2015-11-17)
- 0.2 series: 3 releases (2015-12-02 -> 2016-02-17)
- 0.3 series: 6 releases (2016-03-11 -> 2016-08-10)
- 0.4 series: 25 releases (2016-09-08 -> 2018-09-12, 2019-04-29)
- 0.5 series: 17 releases (2018-11-13 -> 2019-12-17, 2020-03-17)
- 0.6 series: 6 releases (2019-12-17 -> 2020-04-09)
- Breaking releases come out around Devcon: 0.4.0, 0.5.0

Some random facts:
- 0.1.0 was released 2015-07-10 (but no build is available)
- 0.1.1 on 2015-08-04 and is the oldest on solc-bin
- 0.1.2 on 2015-08-20 and is the oldest on the github release page
- 0.1.3 on 2015-09-25 introduced `throw` statement (who remembers it?)
- 0.1.5 on 2015-10-17 first breaking change in "ABI":
> Encode short byte arrays and strings together with their length in storage.
- 0.2.0 on 2015-12-02 first breaking change in language:
> `new ContractName.value(10)()` has to be written as `(new ContractName).value(10)()`
- 0.2.1 on 2016-01-30 introduced `imports`
- 0.3.0 on 2016-03-11
- 0.3.1 on 2016-03-31 introduced inline assembly
- 0.3.3 on 2016-05-27 inlined `internal` library functions
- 0.3.6 on 2016-08-10 "why3" formal verification backend (long gone)
- 0.4.0 on 2016-09-08 over 16 breaking changes (safety), version pragma, payable keyword
- 0.4.7 on 2016-12-15 metadata hash!
- 0.4.10 on 2017-03-15 assert, require, revert, transfer
- 0.4.11 on 2017-05-03 interfaces, "standard json"
- 0.4.12 on 2017-07-03 lots of new yul features
- 0.4.16 on 2017-08-24 smtchecker, pure, view, abiencoderv2
- 0.4.25 on 2018-09-12 last regular 0.4 release
- 0.5.0 on 2018-11-13 monster breaking release (at least 6 months late), over 60 breaking changes
- 0.6.0 on 2019-12-17 over 30 breaking changes






# Musings on language design

---

### Solidity evolves rapidly

---

### Solidity evolves rapidly

And this is useful!

---

### Solidity evolves rapidly

And this is useful!

And this is needed!

---

### Random trivia #1

July 2015:
- 0.1.0 first release (but no build is available)

August 2015:
- 0.1.1 the oldest on solc-bin
- 0.1.2 the oldest on the github release page

September 2015:
- 0.1.3 introduced `throw` statement (who remembers it?)

---

### Random trivia #2

October 2015:
- 0.1.5 first breaking change in "ABI":
> Encode short byte arrays and strings together with their length in storage.

December 2015:
- 0.2.0 first breaking change in language:
> `new ContractName.value(10)()` has to be written as `(new ContractName).value(10)()`

---

### Random trivia #3

January 2016:

- 0.2.1 introduced `imports`

March 2016:
- 0.3.0 made libraries usable (and reserved the assembly keyword)
- 0.3.1 introduced inline assembly

May 2016:
- 0.3.3 inlined `internal` library functions

---

### Random trivia #4

August 2016:
- 0.3.6 introduced "why3" formal verification backend (long gone)

September 2016:
- 0.4.0 over 16 breaking changes (safety), version pragma, payable keyword

December 2016:
- 0.4.7 metadata hash!

---

### Random trivia #4

March 2017:
- 0.4.10 assert, require, revert, transfer

May 2017:
- 0.4.11 interfaces, "standard json"

July 2017:
- 0.4.12 lots of new yul features

---

### Random trivia #5

August 2017:
- 0.4.16 smtchecker, pure, view, abiencoderv2

September 2018:
- 0.4.25 last regular 0.4 release

November 2018:
- 0.5.0 monster breaking release (at least 6 months late), over 60 breaking changes

December 2019:
- 0.6.0 over 30 breaking changes

---

### Reason: Goals have shifted.

Initial goal: friendly language to attract developers.

Meaning:
- Looking like Javascript
- Allowing weird things
- ~~Lacking features~~ Easy to learn

---

### 2015

```solidity
// basically this is an int to hexstring function, but limited to 160 bits
function addressToBytes(address _address) internal returns (bytes) {
  uint160 tmp = uint160(_address);

  // 40 bytes of space, but actually uses 64 bytes
  string memory holder = "                                              ";
  bytes memory ret = bytes(holder);

  // NOTE: this is written in an expensive way, as out-of-order array access
  //       is not supported yet, e.g. we cannot go in reverse easily
  //       (or maybe it is a bug: https://github.com/ethereum/solidity/issues/212)
  uint j = 0;
  for (uint i = 0; i < 20; i++) {
    uint _tmp = tmp / (2 ** (8*(19-i))); // shr(tmp, 8*(19-i))
    uint nb1 = (_tmp / 0x10) & 0x0f;     // shr(tmp, 8) & 0x0f
    uint nb2 = _tmp & 0x0f;
    ret[j++] = byte(nibbleToChar(nb1));
    ret[j++] = byte(nibbleToChar(nb2));
  }

  return ret;
}
```

---

### 2016

```solidity
function strConcat(string _a, string _b, string _c, string _d, string _e) internal returns (string){
    bytes memory _ba = bytes(_a);
    bytes memory _bb = bytes(_b);
    bytes memory _bc = bytes(_c);
    bytes memory _bd = bytes(_d);
    bytes memory _be = bytes(_e);
    string memory abcde = new string(_ba.length + _bb.length + _bc.length + _bd.length + _be.length);
    bytes memory babcde = bytes(abcde);
    uint k = 0;
    for (uint i = 0; i < _ba.length; i++) babcde[k++] = _ba[i];
    for (i = 0; i < _bb.length; i++) babcde[k++] = _bb[i];
    for (i = 0; i < _bc.length; i++) babcde[k++] = _bc[i];
    for (i = 0; i < _bd.length; i++) babcde[k++] = _bd[i];
    for (i = 0; i < _be.length; i++) babcde[k++] = _be[i];
    return string(babcde);
}
```

(Hint: `abi.encodePacked` in 2018)

---

### Reason: Goals have shifted.

Current goal: safe(r) language trying to stay friendly.

Meaning:
- Solidity is verbose
- Solidity is explicit
- Solidity tries to highlight "risky" constructs (gas usage)

---

### Reason: Ethereum is still learning.

Protocol and EVM developers are busy coming up with
- new features
- new restrictions
- new repricings
- new protocols (Eth 2.0)

---

### Reason: The ecosystem is still learning.

Developers are doing all sorts of things.

Careful balance:
- Do not hold their hands too tight
- Do not let them run around naked

---

### Reason: Auditors are still learning.

It took a few years for the security community to reach a healthy size.

And to build the necessary tools aiding their work.

---

### Reason: We are still learning.

The Solidity community is still figuring out
- what features are needed or are bad,
- what is good or bad syntax,
- what is not enough or too much verbosity,
- how to deliver changes quickly to developers,
- etc.

---

These five reasons show that we still need changes and we need them fast.

---

### How do we conduct language design now?

- Discuss on issues
- Discuss in gitter
- Weekly meetings (Monday, Wednesday)
- Solidity Summit (!!)

---

### And in the future?

1. Agile language design working group
2. More structured proposals (Python PEP, Swift Evolution)
3. Traditional language committee (2-3 year cycles)

---

### New Solidity compilers

It would be nice working more closely together.

---

### Random trivia


