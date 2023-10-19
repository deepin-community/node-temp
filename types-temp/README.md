# Installation
> `npm install --save @types/temp`

# Summary
This package contains type definitions for temp (https://github.com/bruce/node-temp).

# Details
Files were exported from https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types/temp.
## [index.d.ts](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types/temp/index.d.ts)
````ts
// Type definitions for temp 0.9
// Project: https://github.com/bruce/node-temp
// Definitions by: Daniel Rosenwasser <https://github.com/DanielRosenwasser>
// Definitions: https://github.com/DefinitelyTyped/DefinitelyTyped

/// <reference types="node" />

import * as fs from "fs";

declare namespace temp {
  interface OpenFile {
    path: string;
    fd: number;
  }

  interface Stats {
    files: number;
    dirs: number;
  }

  interface AffixOptions {
    prefix?: string | undefined;
    suffix?: string | undefined;
    dir?: string | undefined;
  }

  let dir: string;

  function track(value?: boolean): typeof temp;

  function mkdir(affixes: string | AffixOptions | undefined, callback: (err: any, dirPath: string) => void): void;
  function mkdir(affixes?: string | AffixOptions): Promise<string>;

  function mkdirSync(affixes?: string | AffixOptions): string;

  function open(affixes: string | AffixOptions | undefined, callback: (err: any, result: OpenFile) => void): void;
  function open(affixes?: string | AffixOptions): Promise<OpenFile>;

  function openSync(affixes?: string | AffixOptions): OpenFile;

  function path(affixes?: string | AffixOptions, defaultPrefix?: string): string;

  function cleanup(callback: (err: any, result: Stats) => void): void;
  function cleanup(): Promise<Stats>;

  function cleanupSync(): boolean | Stats;

  function createWriteStream(affixes?: string | AffixOptions): fs.WriteStream;
}

export = temp;

````

### Additional Details
 * Last updated: Fri, 02 Jul 2021 21:32:14 GMT
 * Dependencies: [@types/node](https://npmjs.com/package/@types/node)
 * Global values: none

# Credits
These definitions were written by [Daniel Rosenwasser](https://github.com/DanielRosenwasser).
