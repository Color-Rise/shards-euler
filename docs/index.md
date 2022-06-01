# Welcome

## Basic setup

We will be using [Visual Studio Code](https://code.visualstudio.com/) although any text editor could work.

You will also need a compiled version of Shards to run the solutions. Shards can be [built from the sources](https://docs.fragcolor.xyz/contribute/code/building-shards/).

--8<-- "includes/license.md"

Built on {{ (git.date or now()).strftime("%b %d, %Y at %H:%M:%S") }}{% if git.status %} from commit [{{ git.short_commit }}](https://github.com/color-rise/shards-euler/commit/{{ git.commit }}){% endif %}.
