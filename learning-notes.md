# Notes

## Repo Walkthrough & Yarn Workspace

Yarn workspaces requires an array of file blobs. Anything under packages will be
regarded as single use pacakges.

(Info about require resolve)
[https://nodejs.org/api/modules.html#modules_all_together]

## Cleaning output & rimraf

Adding tsconfig allow single command to build all subpackages

```json
    "composite": true,
```

is needed within the tsconfig.js in order to only build things related to that
package not others.

As there are a number of different caching layers it usefult o use rimraf to
cleatr out build out and bring things back into sync

```cmd
 rm -rf */*.tsbuildinfo */dist
```

When working with yarn workspaces deps should be mostly added at package level
unless for shared config packages.

## Volta

volta can be used to pin certain version packakge and switch on per package
basis (volta)[https://docs.volta.sh/]