# Vercel AI SDK - Mistral Provider

The Mistral provider contains language model support for the Mistral chat API.
It creates language model objects that can be used with the `generateText`, `streamText`, `generateObject`, and `streamObject` AI functions.

## Setup

The Mistral provider is available in the `@ai-sdk/mistral` module. You can install it with

```bash
npm i @ai-sdk/mistral
```

## Provider Instance

You can import `Mistral` from `ai/mistral` and initialize a provider instance with various settings:

```ts
import { Mistral } from '@ai-sdk/mistral';

const mistral = new Mistral({
  baseUrl: '', // optional base URL for proxies etc.
  apiKey: '', // optional API key, default to env property MISTRAL_API_KEY
});
```

The AI SDK also provides a shorthand `mistral` import with a Mistral provider instance that uses defaults:

```ts
import { mistral } from '@ai-sdk/mistral';
```

## Chat Models

You can create models that call the [Mistral chat API](https://docs.mistral.ai/api/#operation/createChatCompletion) using the `.chat()` factory method.
The first argument is the model id, e.g. `mistral-large-latest`.
Some Mistral chat models support tool calls.

```ts
const model = mistral.chat('mistral-large-latest');
```

Mistral chat models also support additional model settings that are not part of the [standard call settings](/docs/ai-core/settings).
You can pass them as an options argument:

```ts
const model = mistral.chat('mistral-large-latest', {
  safePrompt: true, // optional safety prompt injection
});
```
