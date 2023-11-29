# Install guide

__Install Julia__
Juliaup is an installer and version manager https://github.com/JuliaLang/juliaup. This is a recommended way to manage Julia versions.

After installing, run `julia` to obtain the Julia _REPL_.

__Julia environments__
[(Documentation)](https://pkgdocs.julialang.org/v1/environments/#Using-someone-else's-project)

This project's environment is stored in _Project.toml_. You can interactively add packages to an environment by using the Julia command line _REPL_ and _package manager_.  Start Julia and change to the project folder. Type `]` to enter the package manager. Type `activate .` to activate or create an environment specified by _Project.toml_ located in the current folder. Separately, you generate a manifest (solving the versions to create a valid environment) by running `instantiate`; instantiate will check that the environment is correct after you add all the packages you want.

__Adding packages__
[(Documentation)](https://pkgdocs.julialang.org/v1/managing-packages/#Adding-packages) So what packages do you need for this notebook? The simplest cell for each of the notebooks looks something like the following:
```Julia
using QuantumCollocation
using NamedTrajectories
using TrajectoryIndexingUtils

using LinearAlgebra
using CairoMakie
```

First, let's install the standard library packages. From the package manager and in the current environment (type `julia`, `]`, and `activate .`), you can type `add LinearAlgebra` to install and precompile _LinearAlgebra_. Same with `CairoMakie`. These are like Numpy and Matplotlib.

The first three packages (_QuantumCollocation_, _NamedTrajetories_, _TrajectoryIndexingUtils_) are parts of the package [Piccolo](https://docs.juliahub.com/General/Piccolo/stable/), so we could do `add Piccolo`. Alternatively, we can use the git repo's directly, allowing us to keep the cutting edge of these packages or make local changes. Find the git repos on [Aaron's Github page](https://github.com/aarontrowbridge) and clone them to some folder. Then use e.g. `dev ../relative/path/to/repo/QuantumCollocation` to install a development version of _QuantumCollocation_ pointing to the local Github code instead of the Julia package. You can repeat this for the others, also.

Now you can run Julia notebooks in vscode _if you add the julia extension_. Upon opening this folder in VS code, you will see that you default to using the environment based on the _Project.toml_ we created.

# Helpful tips
__Fonts in Visual Studio Code__ VS Code will not display all characters allowed by Julia. You can change the editor font family in the settings to something like `'JuliaMono', 'Source Code Pro', Consolas, 'Courier New', monospace` to get better support from JuliaMono.