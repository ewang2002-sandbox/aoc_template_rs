# Advent of Code Template: Rust
A simple [Advent of Code](https://adventofcode.com/) template repository for Rust.

## Features
This template repository is similar to many other template repositories, if not more basic. However, this template repository uses several [PowerShell](https://learn.microsoft.com/en-us/powershell/scripting/overview) scripts to handle creating and running solution files for you.

<details>
<summary>Scripts</summary>
<br> 

There are two scripts in this repository that can be used.

### `run.ps1`
This script automatically handles running `cargo run` for you, with the specified day.

The command can be executed like so:
```
./run <day> -r <0 or 1>
```
Here, the parameters are:
- `<day>`: an integer corresponding to the solution file that you want to execute.
- `-r <0 or 1>`: whether to run your solution in debug mode (`0`) or release mode (`1`). If no arguments are specified, this will be `0`. 

For example, to run your solution for day 5, run
```
./run 5
```
To run your solution for day 5 in _release_ mode, run
```
./run 5 -r 1
```

### `create.ps1`
This script automatically handles the following:
- creating a new solution file for you.
- updating the `mod.rs` file in the `src/aoc` folder to include this solution file.
- creating the corresponding blank input file for you.
- updating the `run.rs` file in the `src` folder so that the solution file is recognized when compiled.

The command can be executed like so:
```
./create <day>
```
Here, the only parameter is:
- `<day>`: an integer corresponding to the solution file that you want to create.

For example, to create a new solution file for day 10, run
```
./create 10
```
This command will exit with a failure status code if there is a solution file for the specified day; this also means that nothing will be overwritten if this is the case.

</details>

<details>
<summary>Motivation</summary>
<br> 

Essentially, my motivation came down to me not wanting to commit 25 Rust solution files at the very beginning. I also didn't want to manually add the solution files, because that would mean having to update several other files (which was annoying after a while).

Since Rust doesn't support conditional compilation by file, and (as far as I'm aware) Rust macros can't really do this, the next best thing is to write some scripts that can automatically generate these files and then update the other key files. 

</details>

## Requirements
Make sure you have [Rust](https://www.rust-lang.org/) and [PowerShell](https://learn.microsoft.com/en-us/powershell/) installed. If you're using Windows, PowerShell should be available.

## Notes
- Do not edit `src/run.rs`; your changes will be overwritten when you run `./create`.
- Avoid editing `src/aoc/mod.rs`. 
- You are free to add other helper files and edit other files as needed.

## License
MIT.