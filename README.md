# Rails + Docker Template

Rails blog with comments.

## How to run on local machine

In addition to [Ruby](https://www.ruby-lang.org/en/) and [Rails](https://rubyonrails.org/), you also need [nodejs](https://nodejs.org/en/download/) and [yarn](https://yarnpkg.com/lang/en/docs/install) installed.

Run `yarn && bundle && rails s` to start the application.

## How to run with Docker

You need `docker` and `docker-compose` installed.

## Provisioning

Run the following commands to prepare your Docker dev env:

```sh
$ docker-compose build
$ docker-compose run runner yarn install
$ docker-compose run runner ./bin/setup
```

It builds the Docker image, installs Ruby and NodeJS dependencies, creates database, run migrations and seeds.

You're all set! Now you're ready to code!

## Commands

- Running the app:

You can run the Rails up using the following command:

```sh
$ docker-compose up rails
```

If you want to run Webpack Dev server as well:

```sh
$ docker-compose up rails webpacker
```

## Dip

You can also use [`dip`](https://github.com/bibendi/dip)–CLI utility for straightforward provisioning and interacting with an applications configured by `docker-compose`.

To install `dip` copy and run the command below:

```sh
$ gem install dip
```

Then use the following commands:

```sh
# provision application
dip provision

# run web app with all debuging capabilities (i.e. `binding.pry`)
dip rails s

# run rails console
dip rails c

# run webpacker dev server
dip up -d webpacker
# `-d` - mean that service will run in detached (background) mode
```
