# soultokens
Demo repo for testing out possible Soul token usecases using Cosmos SDK.

## About Soul Bonded tokens:

By Vitalik: https://vitalik.ca/general/2022/01/26/soulbound.html

Potential usecases:

App specific user authentication and authorization.
- a unique non-transferrable token can be used to regulate user's access right and authorizations within an application specific context.
- specific operations may be permitted or denied depending on the existence of an Auth token
- identity verification (possibly KYC)
- document holder verification -> can hold data about specific documents issued by an institution (ie. a college Diploma or some certificates)
- avoids the usage of address whitelists/blacklists and instead parses the token data

Basic functionality:
- The token may be issued by an authority (auth mints it and transfers it to the user) or minted by the user.
- this type of token cannot be transfferred, sold or burned
- token data may be updated to reflect changes in authorization or some other application specific context
- there bay be multiple Auth tokens held by an address - each Auth token "unlocks" a specific set of functionalities that may be available for a particular API or a web3 app. (the token is application/context specific)


### Example use case: Distributed Storage app

A distributed storage app may have multiple levels of access.
For instance, there may be 2 sets of users that share access to a particular resource (that resource being a service account in this case):
- admin user
- basic user

Basic users may be permitted to have read access to some data. That data may be the lists of uploaded files, or the files themselves.
On the other hand admin users have the ability to do read, write and delete operations.

In order to excercise the rights, the user's address will be checked for the Auth token existence. The application then permits certain actions depending on the settings outlined by the token.

## Get started

```
ignite chain serve
```

`serve` command installs dependencies, builds, initializes, and starts your blockchain in development.

### Configure

Your blockchain in development can be configured with `config.yml`. To learn more, see the [Ignite CLI docs](https://docs.ignite.com).

### Web Frontend

Ignite CLI has scaffolded a Vue.js-based web app in the `vue` directory. Run the following commands to install dependencies and start the app:

```
cd vue
npm install
npm run serve
```

The frontend app is built using the `@starport/vue` and `@starport/vuex` packages. For details, see the [monorepo for Ignite front-end development](https://github.com/ignite/web).

## Release
To release a new version of your blockchain, create and push a new tag with `v` prefix. A new draft release with the configured targets will be created.

```
git tag v0.1
git push origin v0.1
```

After a draft release is created, make your final changes from the release page and publish it.

### Install
To install the latest version of your blockchain node's binary, execute the following command on your machine:

```
curl https://get.ignite.com/msalopek/soultokens@latest! | sudo bash
```
`msalopek/soultokens` should match the `username` and `repo_name` of the Github repository to which the source code was pushed. Learn more about [the install process](https://github.com/allinbits/starport-installer).

## Learn more

- [Ignite CLI](https://ignite.com/cli)
- [Tutorials](https://docs.ignite.com/guide)
- [Ignite CLI docs](https://docs.ignite.com)
- [Cosmos SDK docs](https://docs.cosmos.network)
- [Developer Chat](https://discord.gg/ignite)
