# Hugo Microtypo

That project is a try to build a Hugo module by porting [Jekyll Microtypo](https://github.com/borisschapira/jekyll-microtypo)


## Requirements

* Git
* Hugo > v0.56.0
* go >= 1.12

## Installation

1. (Optional) If your hugo site is not already a Go module, initialize it with `hugo mod init` and the URL of your repository at the root of your project:

`hugo mod init github.com/username/repository`

It should create a `go.mod` file.

2. Add the module to your Hugo configuration file:

TOML example:

```toml
[module]

  [[module.imports]]
      path="github.com/jygastaud/hugo-microtypo/microtypo"
      disable=false
```

YAML example:
```yaml
module:
  imports:
    - path: github.com/jygastaud/hugo-microtypo/microtypo
      disable: false
```

3. Import the module

```
hugo mod get github.com/jygastaud/hugo-microtypo/microtypo
```

## Usage

* Replace any `{{ .Content }}` call by `{{ partial "content.html" .Content }}`
* Rebuild your site and you're done :tada:

You can also use the content.html partial to replace any variable such as: `.Summary`...

Some examples:

```
{{ partial "content.html" .Content }}
{{ partial "content.html" .Summary }}
```

## Options

A new params is available to enable/disable usage of aria-hidden when "Point Median" is used.
Default to `false`.

To change that value, add a new param `pointMedian = true` inside your config.toml.


## Contribute

Note that we can not guarrenty any maintenance of that plugin (yet) but we will do our best.

Be sure that we would more than happy to review any pull request.

If you need to work locally on the module, you can add that line at the end of your `go.mod` file:

```
replace github.com/jygastaud/hugo-microtypo/microtypo => /<your-path>/hugo-microtypo/microtypo
```

## Projects using Hugo Microtypo

- Good Impact Base Structure [![Good Impact Base Structure - Gitlab](https://img.shields.io/badge/GitLab-330F63?style=for-the-badge&logo=gitlab&logoColor=white)]([https://github.com/cnumr/EcoIndex/](https://gitlab.com/goodimpact/goodimpact-hugo/modules/base-structure))  
  … used by [EcoIndex.fr](https://www.ecoindex.fr/) [![GitHub EcoIndex](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/cnumr/EcoIndex/)
