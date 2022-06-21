# Tutorial Git Secret

## Install

Lihat https://git-secret.io/installation

## Persiapkan GPG

Buat kunci baru:

```bash
gpg --gen-key
```

Export GPG:

```bash
gpg --armor --export your.email@address.com > public-key.gpg
```

Import GPG:

```bash
gpg --import public-key.gpg
```

## Persiapkan Simple Git Hooks

```bash
npm i -g simple-git-hooks
```

## Init Git Secret di Repositori

Tambahkan ini di `package.json`:

```json
{
  "simple-git-hooks": {
    "pre-commit": "git secret hide"
  }
}
```

```bash
simple-git-hooks
git secret init
git secret tell -m
```

## Tambahkan File ke Git Secret

```bash
git secret add namaFilenya.txt
```

## Decrypt File Setelah Clone

```bash
git secret reveal
```