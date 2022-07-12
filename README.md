# Tools for using nft.storage

```bash
npm install -g nft-cli
```

## Pack directory into `.car` file

Content Addressable aRchive ([`.car`](https://github.com/ipld/js-car)) is an archive file that stores files in the same manner as IPFS. This makes uploading it to an IPFS compatible endpoint easy.

```bash
nft pack <file or directory> --output <path/to/file.car> # default is ./index.car
```

Note: this will not include the directory in the file, e.g. if you had the following `dir/a`

```bash
nft pack dir
```

generates `index.car` which includes `a` but not `dir`.

For example, 

```
- nft_project_directory
  - 0.png
  - 0.json
  - ...
```
Then using the cli:
```
nft pack nft_project_directory
```


Produces an `index.car`, which contains the files in the directory.

## Upload

Requires the environment variable `NFT_STORAGE_API_TOKEN` or `--api-key ...` from [`nft.storage`](https://nft.storage)

```bash
nft upload index.car
```

```bash
nft upload index.car --api-key # fill in here
```
