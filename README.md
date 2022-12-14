# Advent of Code Elixir Starter

A batteries included starter pack for participating in [Advent of Code](https://www.adventofcode.com) using Elixir!

## Usage

There are 25 modules, 25 tests, and 1 mix task.

1. Fill in the tests with the example solutions.
1. Write your implementation.
1. Fill in the final problem inputs into the mix task and run `mix advent -d 1`!
   - Benchmark your solution by passing the `-b` flag, `mix advebt -d 1 -b`

```elixir
defmodule AdventOfCode.Day01 do
  def part1(args) do
  end

  def part2(args) do
  end
end
```

```elixir
defmodule AdventOfCode.Day01Test do
  use ExUnit.Case

  import AdventOfCode.Day01

  @tag :skip # Make sure to remove to run your test.
  test "part1" do
    input = nil
    result = part1(input)

    assert result
  end

  @tag :skip # Make sure to remove to run your test.
  test "part2" do
    input = nil
    result = part2(input)

    assert result
  end
end
```

### mix advent

The `mix advent` task accepts combination of following arguments:

- `-y` or `--year` year of the advent of code (default value current year)
- `-d` or `--day` day
- `-p` or `--part` part `1` or `2` (default value `1`)
- `-b` or `--benchmark` whether to benchmark the run

### Optional Automatic Input Retriever

This starter comes with a module that will automatically get your inputs so you
don't have to mess with copy/pasting. Don't worry, it automatically caches your
inputs to your machine so you don't have to worry about slamming the Advent of
Code server. You will need to configure it with your cookie and make sure to
enable it. You can do this by creating a `config/secrets.exs` file containing
the following:

```elixir
import Config

config :advent_of_code, AdventOfCode.Input,
  allow_network?: true,
  session_cookie: "..." # yours will be longer
```

After which, you can retrieve your inputs using the module:

```elixir
day = 1
year = 2020
AdventOfCode.Input.get!(day, year)
# or just have it auto-detect the current year
AdventOfCode.Input.get!(7)
# and if your input somehow gets mangled and you need a fresh one:
AdventOfCode.Input.delete!(7, 2019)
# and the next time you `get!` it will download a fresh one -- use this sparingly!
```

## Installation

```bash
# clone
$ git clone git@github.com:martinhrvn/advent-of-code-elixir-starter.git advent-of-code
$ cd advent-of-code

# Reinitialize your git repo
$ rm -rf .git && rm -rf .github
$ git init
```

### Get started coding with zero configuration

#### Using Visual Studio Code

1. [Install Docker Desktop](https://www.docker.com/products/docker-desktop)
1. Open project directory in VS Code
1. Press F1, and select `Remote-Containers: Reopen in Container...`
1. Wait a few minutes as it pulls image down and builds Dev Conatiner Docker image (this should only need to happen once unless you modify the Dockerfile)
   1. You can see progress of the build by clicking `Starting Dev Container (show log): Building image` that appears in bottom right corner
   1. During the build process it will also automatically run `mix deps.get`
1. Once complete VS Code will connect your running Dev Container and will feel like your doing local development
1. If you would like to use a specific version of Elixir change the `VARIANT` version in `.devcontainer/devcontainer.json`
1. If you would like more information about VS Code Dev Containers check out the [dev container documentation](https://code.visualstudio.com/docs/remote/create-dev-container/?WT.mc_id=AZ-MVP-5003399)

#### Compatible with Github Codespaces

1. If you dont have Github Codespaces beta access, sign up for the beta https://github.com/features/codespaces/signup
1. On GitHub, navigate to the main page of the repository.
1. Under the repository name, use the Code drop-down menu, and select Open with Codespaces.
1. If you already have a codespace for the branch, click New codespace.
