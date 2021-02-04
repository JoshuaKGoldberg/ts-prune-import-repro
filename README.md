# ts-prune import repro

With these files:

```ts
// ambient.ts

let box: import("./types").Box = {
  value: "",
};

console.log({ box });
```

```ts
// types.ts

export interface Box {
    alias?: string;
    value: string;
}
```

`ts-prune` will incorrectly flag `Box` as unused.

## Usage

```shell
npm i
npm test
```