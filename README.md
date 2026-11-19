# mule

Mule answers one-off questions using the web and your notes. Ask from the
command line or in a browser.

## Install

Install mule 0.1.0 with Homebrew:

```sh
brew install stevenjpx2/taps/mule
```

## Set up your sources

Create `mule.config.ts` to choose your model, sources and skills directory:

```ts
export default {
  model: "anthropic/claude-haiku-5",
  mcps: ["web", "notes"],
  skills: ["~/.config/mule/skills"],
};
```

The web source looks up information on the web. The notes source searches your
own notes. Skills in `~/.config/mule/skills` give Mule instructions for your
recurring tasks.

## Ask what changed this week

Ask about Sourcefed:

```sh
mule "what changed in sourcefed this week?"
```

Mule looks through the web and your notes for relevant material and responds
with a summary of the week’s changes.

```mermaid
flowchart LR
    You["You"] -->|"Sourcefed question"| Mule["Mule"]
    Mule -->|"Look up this week"| Sources["Web and your notes"]
    Sources -->|"Relevant material"| Mule
    Mule -->|"Summary of changes"| You
```

## Ask in a browser

Open the same experience in a browser tab:

```sh
mule --web
```

## Ask Mule to remember

Mule remembers across questions only when you explicitly ask it to.

## Roadmap

- [ ] One-off questions in the CLI and browser
- [ ] Web and notes sources with skills from your directory
- [ ] Memory across questions only when explicitly requested
- [ ] Publish mule 0.1.0 to the stevenjpx2/taps tap

## More

- [Design](https://github.com/wrkhse/mule/issues/1)
- [Harness notes](https://github.com/wrkhse/tack/issues/26)
- [Workhorse philosophy](https://github.com/wrkhse/workhorse/blob/main/PHILOSOPHY.md)
