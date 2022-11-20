# bacula-web.org website

## About this git repository

This repository contains the code of Bacula-Web website content.
Bacula-web website is built using [Hugo](https://gohugo.io/).

## Contributing

You can contribute to this git repository by following the steps below

- fork this [project](https://github.com/bacula-web/www.bacula-web.org) on Github
- commit your changes / fixes
- create a pull request

## License

Content of this website is licensed under [GNU GPL version 2](https://www.gnu.org/licenses/old-licenses/gpl-2.0.html)

## Running the website locally using Docker

Clone the git repository

```shell
git clone https://github.com/bacula-web/www.bacula-web.org.git
```

and run this command to open a shell in a Docker container

```shell
docker run --rm -i -t -v $(pwd):/src --name bacula-web-website -p 1313:1313 klakegg/hugo:<tag> shell
```

## Build

```shell
docker run --rm -it -e HUGO_ENV=production -v $(pwd):/src klakegg/hugo:0.105.0-ext-alpine -b https://www.bacula-web.org
```

Open a terminal into the Docker container

```shell
cd www.bacula-web.org
docker exec -i -t bacula-web-website bash
```

then start Hugo builtin web server

```shell
hugo server

# To show content in draft, run this command
hugo server -D
```

You can also run this command

```shell
docker run --rm -it -v $(pwd):/src --name website -p 1313:1313 klakegg/hugo:0.105.0-ext-alpine server -D
```

### Quick note related to git sub-module

> After cloning this Git repository, as Hugo theme is setup as a git submodule, you need to run the command below
> `git submodule update --init --recursive`
>
> For more details, see [Git tools submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules)
