# 2020-12-09
## Proposed Agenda
* @dcode [asc-native](https://github.com/dcodeIO/asc-native)
  * Compiles and runs
  * assemblyscript/src -> untouched 961Kb, optimized ~ 641Kb - just STD it uses. Compiler is a library. No cli interface or sources.
  * GC: Binaryen is working on GC, new instructions [PR](https://github.com/WebAssembly/binaryen/pull/3433)
  * [Discussions feature on GH repo to create threads](https://github.com/AssemblyScript/assemblyscript/discussions).
    * Q&A section similar to StackOverflow.
    * Also can do an AMA.
    * FAQ 
* @torch2424 nothing to report
  * Bytecode Alliance stuff is moving forward!
  * Fastly AS feedback has been positive
* @jtenner [as-pect updated](https://github.com/jtenner/as-pect/releases/tag/v5.0.0)!
* @willemneal asb updates 


# 2020-11-11
## Proposed Agenda
* @saulecabrera - Future of AS at Shopify.
  * Looking to have open Beta of AS product
  * Will extend AS to thousands of Devs
  * Feedback:
    * Current customers used to dynamic languages, e.g. ones with closures.
    * Documentation for AS/Devs confused with TS.
    * Lack of insightful errors.
  * Where we are next steps:
    * Three options:
      * Maintain a fork of closures and add features
      * See if it is feasible to add Compile flags for nightly features
      * Try another language and return once AS has stablized
         * @torch2424 Fastly supports multiple languages
 * @torch2424 - 
    * URL imlpmentation in AS, string parser to URL object
    * Include bytes wanted: https://github.com/willemneal/visitor-as/blob/master/dist/examples/includeBytesTransform.js
    * About to work on json
    * fixed asbind issues
* @willemneal and @jtenner
   * Working on updating as-pect to use the new runtime: https://github.com/jtenner/as-pect/pull/316
* @trusktr 3.js -> Wasm
   * issues from closures haven't been clear.
   * error messages are misaligned.
   * Looking forward to use @battlelinegames' ASGlue
   * New member to lume/glas suggested 3.js -> TS merging
* battlelinegames - had success with generating AS files from wave front files
* @dcode presented about stack-agnostic deferred Reference Counting (sad RC)
  * Add `gcNext` pointer to object header
  * Add `__defer`, `__commit`, `__commit_with_value`
  * Each function has its own autorelease pool


# 2020-10-28
## Proposed Agenda
* @willemneal found https://firstcontributions.github.io/.
  * will add PR to add to this list: Use Org link
* @torch2424 [Fastly relased AS runtime](https://twitter.com/torch2424/status/1321551389613461504), that they will support AS and publish AS runtime for serverless apps!
  * Built fetch API in AS.  Not full interface, but allows fetch and response calls.
  * Got WasmBoy to run on the edge!
  * Planning is starting for 2021 WasmSummit
* @battlelinegames trying to convert wave front files into AS files. Putting data into binary could be big, but web models tend to be smaller.


# 2020-10-14
## Proposed Agenda
* @torch2424
  * Updates to asbind to edit memory directly
  * BCA - internal stuff that is causing delays.
  * Finished AS demos
  * Hook up with Saul about closures and Lang server.
  * Feb 2021 WasmSummit
* @battlelinegames Adding examples to WebGL and fixing bugs along the way.
* @willemneal added 'exportAs' decorator to rename to any name with visitor-as.
* @ospencer Grain updates: Got help from AS community.
   * Hacktoberfest has helped with bugs.
* @dcode switched to working on Runtime.  Updated allocator to separate runtime allocation and malloc/free. Tests are mostly passing.
* @truskr will use @battlelinegames's [ASWebGLue](https://github.com/battlelinegames/ASWebGLue) to finish [glas](https://github.com/lume/glas).

# 2020-9-16

## Proposed Agenda
* @battlelinegames new Game! https://embed.com/wasm/asteroid/
  * @torch2424 helped with sound
  * Should there be a tutorial, @DuncanUszkay1 "could lead to interest and contributors"
  * Function Overloading discussion, Do we break with TS?
   * Need Langage server: https://github.com/saulecabrera/asls
   * Shopify has a LS https://github.com/saulecabrera/asls by @saulecabrera
   * Create our own docs generator
* @torch2424
  * Talk ready
  * Bytecode alliance: TL;DR If we join we follow the rules.
    * Slow moving but progress
    * Still keeping it underwaps for PR purposes
    * Guess is in October!
    * Fastly feedback from devrel requests for a special main function to run before normal main.
* @DuncanUszkay1
  * PR on identifying closures to show what the pass would do
  * Waiting on feedback from @dcode
  * Tests need to be updated
* @dcode Binaryen PR is slow
  * Updated anyref PR now allows all subclasses
* @jayphelps looking to hire someone to help write babel compiler plugins.
  * Hiring later in the fall for other complier roles

# 2020-9-2

## Proposed Agenda
* Introduce new members
* Open floor to members
* @ColinEberhardt has used AS since 2017, used it to write smart contracts on NEAR.  Recreated a meetup style sign up. Easiest path to writing WebAssembly.
  * Most challenging is debugging. [Atari emulator](https://github.com/ColinEberhardt/atari2600-wasm)
  * Date support is an obstacle.
  * Source maps. Look into using DWARF custom section.
* Bytecode Alliance still paused from Mozilla fallout but meetings are coming up.
* Closures
  * @torch2424 writing talks
  * @DuncanUszkay1 hasn't had time, but had meeting with Mozilla people to hire them to continue open source work.  Looking into hiring OS person.
* @decode Binaryen PR, Getting closer.
  * Current discussions on GC requirements: https://github.com/WebAssembly/gc/pull/121
* @battlelinegames's project connect WebGL to AssemblyScript
* @ospencer No updates for grain
* @jayphelps is giving a talk on using binaryen
  * Wasm CG propsode stack suspension/rerun to implement async/await.
* @MaxGraey been working on Binaryen and improving optimizations. `wasmtime` PR's to improve its performance.  Improve JS/AS interopability.
  * {New Universal Texture Transcoders in AS](https://github.com/KhronosGroup/Universal-Texture-Transcoders)
* Amin Yahyaabadi interested in using Wasm in BRowser for ML related tasks.

# 2020-8-19

## Proposed Agenda 
* Introduce Grain team with AS team
* Now have includeBytes see [PR](https://github.com/willemneal/visitor-as/pull/6)
* Closures
  * First class functions merge with old PR
* GC is taking longer than expected
  * adding types
  * six preliminary PRs now
* Waiting to follow up Bytecode Alliance as Mozilla's turn over.
* Grain
  * low hanging fruit with switch with binaryen
  * Remove JS from runtime perhaps switch to AS
  * improve windows support for binaryen
* Regex looking into JS library that builds DFA
* Shopify is looking into use https://github.com/wapc/as-msgpack for serialization.
  * rolled out internal AS scripts for customers, so AS is now used in production.
* Fastly looking into announcing AS soon.

# 2020-8-5

## Proposed Agenda
* Welcome grain team
* Discuss [asbuild](https://github.com/willemneal/asbuild) and future of toolchains
  - Move to AS org
* Discuss [as-link](https://github.com/willemneal/as-link)
* Update on closures
  - Blocked by shopify's schedule
* Binaryen Garbage collection
  - refactorying type internals.
  - In future refactor runtime internals from the compiler. Then create a binaryen pass which will add polyfill where needed.
* Open up for audience
 
# 2020-7-22

## Proposed Agenda
* Welcome new members
* Discuss build tooling and default conventions old PR: https://github.com/AssemblyScript/assemblyscript/pull/1134/files
* Discuss liking; compiling modules where imports are just typed checked and linked at runtime
  - Add bindings similar to wasm-bindgen.
  - Example of a WebGL binding: https://github.com/lume/glas
* Rick's VS extension
* Closure Update
  - Waiting on [Binaryen PR](https://github.com/WebAssembly/binaryen/pull/2586) to be merged.
  - https://github.com/AssemblyScript/assemblyscript/pull/1401
  - AIR - AssemblyScript Intermediate Representation; [Example](https://github.com/AssemblyScript/assemblyscript/blob/air/src/air.ts)
  - Pending PR for closure tests, but might be rewritten
* Plans for new six months
  - Reach out to more projects
  - AIR
  - as-wasm-bindgen, a simple tool to generate JS bindings that are type aware. [A starting point](https://github.com/AssemblyScript/assemblyscript/blob/master/src/definitions.ts#L373)
  - wit, witx support, [as-witx](https://github.com/jedisct1/as-witx)
  - Use wasm-gc opcodes and add polyfill in [binaryen pass.](https://github.com/WebAssembly/binaryen/issues/2935)
    - [wasm-gc](https://github.com/WebAssembly/gc)
    - [Prototype](https://github.com/WebAssembly/gc/issues/81)


# 2020-5-13

## Proposed Agenda
 - Discuss Closures implementation
   - Currently use a global to store the closure to be 
 - Discuss making meetings less frequent


# 2020-04-29

## Proposed Agenda
* Review action items
* Open Forum
* Discuss next action items

### Previous Action items

* Linting
 - Rick made VS extension 
 - Add a parseFile option for complier to be added soon to simplify linting.
* hex/base64 libs
 - Hex is stdlib
 - base64?
 - [SHA-256 lib](https://github.com/ChainSafe/as-sha256)
* Compare the performance of passing complex types through serialier and by writting directly into memory.
  - Future [borsh](https://github.com/near/borsh) implementation in AssemblyScript @willemneal
* ~~Decide where to keep this repo,~~ 


## New Action Items
- ~~create calendar @torch2424~~
- vtables PR @willemneal
- ~~Publish base58/64 @willemneal~~


## News
- [PR on object literal instatianation with optional fields.](https://github.com/AssemblyScript/assemblyscript/pull/1229) @torch2424 
- 0.10.0 release on the horizon.
- Web3 Foundation doesn't want to support crypto develompent without dedicated support.
- [Crypto Wasi on the horizon.](https://github.com/WebAssembly/WASI-crypto)
