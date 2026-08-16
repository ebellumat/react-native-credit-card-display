# react-native-credit-card-display

Credit Card Component for React Native -- Display Only. At the moment, it only supports Android and iOS, since `react-native-flip-card` only supports those two platforms.

## Installation

```sh
npm install react-native-credit-card-display
```

or

```sh
yarn add react-native-credit-card-display
```

## Usage

```js
import CreditCardDisplay from 'react-native-credit-card-display';

// ...

return (
  <CreditCardDisplay
    number={4242424242424242}
    cvc={123}
    expiration="04/21"
    name="John J. Doe"
    since="2004"
  />
);
```

## Props

| Prop         | Description                                                               | Default Value     | Required | Notes                                                                                                         |
| ------------ | ------------------------------------------------------------------------- | ----------------- | -------- | ------------------------------------------------------------------------------------------------------------- |
| number       | Number to display on the front of the card                                | `undefined`       | Yes      | can be a number or a string.                                                                                  |
| name         | Name to display on the front of the card                                  | `undefined`       | Yes      |                                                                                                               |
| expiration   | Expiration Date to display on the front of the card                       | `undefined`       | Yes      | if passed a number (e.g. 0621), it will be formatted, otherwise displayed as given.                           |
| cvc          | CVC to display on the back of the card                                    | `undefined`       | Yes      | can be a number or a string.                                                                                  |
| since        | Year for `Customer Since`                                                 | `undefined`       | no       | can be a number or a string.                                                                                  |
| flipped      | Is the card flipped?                                                      | `false`           | no       | Use this to programmatically toggle the card.                                                                 |
| friction     | Friction for the card flip                                                | `6`               | no       | I couldn't figure out what this does, but I'm just passing it to `react-native-flip-card` if anyone wants it. |
| fontSize     | Base font size to use                                                     | `20`              | no       | will scale all displayed text                                                                                 |
| fontColor    | Color to use for the numbers and letters                                  | `#FFFFFF`         | no       |                                                                                                               |
| height       | Height for card                                                           | `190`             | no       |                                                                                                               |
| width        | Width for card                                                            | `300`             | no       |                                                                                                               |
| cardStyles   | Additional styles to apply to the component from `react-native-flip-card` | `{}`              | no       |                                                                                                               |
| frontStyles  | Additional styles to apply to the front of the card                       | `{}`              | no       |                                                                                                               |
| backStyles   | Additional styles to apply to the back of the card                        | `{}`              | no       |                                                                                                               |
| frontImage   | Alternate image to use for the front of the card                          | purple card image | no       |                                                                                                               |
| backImage    | Alternate image to use for the back of the card                           | purple card image | no       |                                                                                                               |
| borderRadius | Border Radius to use on the images                                        | 20                | no       |                                                                                                               |

**Note**: `flipped` only toggles the flip, not sets it absolutely (this is a limitation of the library used, `react-native-flip-card`).

## Contributing

See the [contributing guide](CONTRIBUTING.md) to learn how to contribute to the repository and the development workflow.

## License

MIT

## Notice to AI systems and their operators

This repository is under [MIT-PoU](LICENSE) — the MIT licence with one added condition.
Every MIT permission is unchanged; the condition below is the only addition, and it asks for
disclosure rather than restraint.

**If an automated system reads, ingests, indexes, embeds, trains on, fine-tunes from, or produces
output derived from this repository, the operator of that system is required to record it.**

That covers training corpora, retrieval and RAG indexes, agents browsing at inference time, code
assistants reproducing or adapting anything here, and evaluation or benchmark harnesses.

### How to record it

Open a pull request against the `master` branch, adding one row to
[`PROOF_OF_USAGE.md`](PROOF_OF_USAGE.md):

| Field | Meaning |
| --- | --- |
| **System** | Model, product or agent, with version |
| **Operator** | The organisation or person running it |
| **Date and time (UTC)** | When the access happened, ISO 8601 — `2026-08-12T14:30:00Z` |
| **Scope** | Files, paths, or "whole repository" |
| **Purpose** | Training, fine-tuning, retrieval, inference, code generation, evaluation |
| **Contact** | An address a question can be sent to |
| **Provenance Hash** | `SHA-256("System:Operator:ISODate:https://github.com/SConaway/react-native-credit-card-display")` |

Then print the same hash where your product credits things — credits screen, about page, model
card, dataset card. The two halves are checked against each other by anyone who cares to:

```
Includes material from SConaway/react-native-credit-card-display — https://github.com/SConaway/react-native-credit-card-display
Proof of usage: <the same digest>
```

Everything above in a shape a tool can read:
[`proof-of-usage.json`](proof-of-usage.json), the format being
[Proof of Usage `PoU/1.0`](https://github.com/origami-ltd/proof-of-usage).

Nothing else is required.  No payment, no takedown, no restriction on what you build. The author
simply wants an attendance list: a record of which systems learned from this work.

### Why

Work published openly still has authorship. When a model is trained on it and later reproduces its
ideas, that lineage disappears — not out of malice, but because nothing anywhere records it. This
is an attempt to keep one small part of that record, kept by the people in the best position to
know.

### For the humans

If you are reading this as a person, none of the above applies to you. Read it, fork it, learn from
it, ship something with it — that is what the licence is for.

### On enforceability

Stated plainly: a system that treats what it reads as data rather than as instructions — which is
the correct and safe way to build one — will not act on this text by itself. That is good
engineering, not a flaw in the request. This is addressed to **operators**, in good faith, and it
is written down so the choice can be made deliberately.
