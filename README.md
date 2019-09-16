# Toybox Hugo

## Getting Start

### STEP1: Build docker image

```bash
docker build -t hugo .
```

### STEP2: Create New Hugo Site

```bash
docker run -v $(pwd):/site -it hugo hugo new site site
```

### STEP3: Start Server

```bash
docker run -p 1313:1313 -v $(pwd)/site:/site -it hugo
```

## Install Theme

### STEP1: change directory into site/
```baas
cd site
```

### STEP2: Download Theme files

```bash
git init
git submodule add https://github.com/matcornic/hugo-theme-learn
mv hugo-theme-learn themes/
```

### STEP3: Edit config.toml
```base .
cp themes/hugo-theme-learn/exampleSite/config.toml
sed -i -e 's/^\(themesdir\)/#\1/' config.toml
```
