# Changelog

## 1.1.1 (2026-11-28)

- The price estimate reads Wiro's renamed price methods (`per-run`, `per-output-file`, `per-input-character` and the rest), so the estimate before a run and the `max-cost` check work with the current catalog. A row with a method Wiro does not bill by has no price before the run, so `max-cost` does not start it.
- The new `per-input-video-second` is a price per second of input video in the estimate log, and an option's `maxSeconds` is named with it: "$0.025 per second of input video, each input at most 60 seconds".
- The units use Wiro's words: "per prompt character", "per second of output video", "per input and output token".

## 1.1.0 (2026-11-11)

- **Workflow mode.** Run one of your Wiro AI workflows by its link or full slug. `params` sets its inputs and `files` uploads local files for them. The action checks the inputs before it starts, logs each step, returns the End node's results in `outputs`, `urls` and `text`, and downloads files. The new `run-token` output holds the run's token.
- **Cost limit.** The action estimates the price before every run, logs it and sets the new `estimated-cost` output. A run whose estimate is above `max-cost`, or whose price can't be confirmed under it, does not start.
- **Required parameters.** In model mode, a required parameter you leave out, such as an output format, gets the default the model's form on wiro.ai starts with. The log lists them.
- New README examples: a release banner with a short video, the release notes read aloud, a README translation in a pull request, a social share card and a workflow run.
- `mode` can be left out when `workflow` is set, and `model` is no longer marked required, since workflow mode doesn't use it.

## 1.0.0 (2026-11-11)

- First release: model mode and llm mode, local files as inputs, downloads, signature authentication, the job summary, and stopping the task on timeout or cancellation.
