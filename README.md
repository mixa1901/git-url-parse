<!-- Please do not edit this file. Edit the `blah` field in the `package.json` instead. If in doubt, open an issue. -->








[![git-url-parse](http://i.imgur.com/HlfMsVf.png)](#)











# git-url-parse

 [![Support me on Patreon][badge_patreon]][patreon] [![Buy me a book][badge_amazon]][amazon] [![PayPal][badge_paypal_donate]][paypal-donations] [![Ask me anything](https://img.shields.io/badge/ask%20me-anything-1abc9c.svg)](https://github.com/IonicaBizau/ama) [![Travis](https://img.shields.io/travis/IonicaBizau/git-url-parse.svg)](https://travis-ci.org/IonicaBizau/git-url-parse/) [![Version](https://img.shields.io/npm/v/git-url-parse.svg)](https://www.npmjs.com/package/git-url-parse) [![Downloads](https://img.shields.io/npm/dt/git-url-parse.svg)](https://www.npmjs.com/package/git-url-parse) [![Get help on Codementor](https://cdn.codementor.io/badges/get_help_github.svg)](https://www.codementor.io/johnnyb?utm_source=github&utm_medium=button&utm_term=johnnyb&utm_campaign=github)

<a href="https://www.buymeacoffee.com/H96WwChMy" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/yellow_img.png" alt="Buy Me A Coffee"></a>







> A high level git url parser for common git providers.

















## :cloud: Installation

```sh
# Using npm
npm install --save git-url-parse

# Using yarn
yarn add git-url-parse
```













## :clipboard: Example



```js
// Dependencies
const GitUrlParse = require("git-url-parse");

console.log(GitUrlParse("git@github.com:IonicaBizau/node-git-url-parse.git"));
// => {
//     protocols: []
//   , port: null
//   , resource: "github.com"
//   , user: "git"
//   , pathname: "/IonicaBizau/node-git-url-parse.git"
//   , hash: ""
//   , search: ""
//   , href: "git@github.com:IonicaBizau/node-git-url-parse.git"
//   , token: ""
//   , protocol: "ssh"
//   , toString: [Function]
//   , source: "github.com"
//   , name: "node-git-url-parse"
//   , owner: "IonicaBizau"
// }

console.log(GitUrlParse("https://github.com/IonicaBizau/node-git-url-parse.git"));
// => {
//     protocols: ["https"]
//   , port: null
//   , resource: "github.com"
//   , user: ""
//   , pathname: "/IonicaBizau/node-git-url-parse.git"
//   , hash: ""
//   , search: ""
//   , href: "https://github.com/IonicaBizau/node-git-url-parse.git"
//   , token: ""
//   , protocol: "https"
//   , toString: [Function]
//   , source: "github.com"
//   , name: "node-git-url-parse"
//   , owner: "IonicaBizau"
// }

console.log(GitUrlParse("https://github.com/IonicaBizau/git-url-parse/blob/master/test/index.js"));
// { protocols: [ 'https' ],
//   protocol: 'https',
//   port: null,
//   resource: 'github.com',
//   user: '',
//   pathname: '/IonicaBizau/git-url-parse/blob/master/test/index.js',
//   hash: '',
//   search: '',
//   href: 'https://github.com/IonicaBizau/git-url-parse/blob/master/test/index.js',
//   token: '',
//   toString: [Function],
//   source: 'github.com',
//   name: 'git-url-parse',
//   owner: 'IonicaBizau',
//   organization: '',
//   ref: 'master',
//   filepathtype: 'blob',
//   filepath: 'test/index.js',
//   full_name: 'IonicaBizau/git-url-parse' }

console.log(GitUrlParse("https://github.com/IonicaBizau/node-git-url-parse.git").toString("ssh"));
// => "git@github.com:IonicaBizau/node-git-url-parse.git"

console.log(GitUrlParse("git@github.com:IonicaBizau/node-git-url-parse.git").toString("https"));
// => "https://github.com/IonicaBizau/node-git-url-parse.git"
```











## :question: Get Help

There are few ways to get help:



 1. Please [post questions on Stack Overflow](https://stackoverflow.com/questions/ask). You can open issues with questions, as long you add a link to your Stack Overflow question.
 2. For bug reports and feature requests, open issues. :bug:
 3. For direct and quick help, you can [use Codementor](https://www.codementor.io/johnnyb). :rocket:





## :memo: Documentation


### `gitUrlParse(url)`
Parses a Git url.

#### Params

- **String** `url`: The Git url to parse.

#### Return
- **GitUrl** The `GitUrl` object containing:
 - `protocols` (Array): An array with the url protocols (usually it has one element).
 - `port` (null|Number): The domain port.
 - `resource` (String): The url domain (including subdomains).
 - `user` (String): The authentication user (usually for ssh urls).
 - `pathname` (String): The url pathname.
 - `hash` (String): The url hash.
 - `search` (String): The url querystring value.
 - `href` (String): The input url.
 - `protocol` (String): The git url protocol.
 - `token` (String): The oauth token (could appear in the https urls).
 - `source` (String): The Git provider (e.g. `"github.com"`).
 - `owner` (String): The repository owner.
 - `name` (String): The repository name.
 - `ref` (String): The repository ref (e.g., "master" or "dev").
 - `filepath` (String): A filepath relative to the repository root.
 - `filepathtype` (String): The type of filepath in the url ("blob" or "tree").
 - `full_name` (String): The owner and name values in the `owner/name` format.
 - `toString` (Function): A function to stringify the parsed url into another url type.
 - `organization` (String): The organization the owner belongs to. This is CloudForge specific.
 - `git_suffix` (Boolean): Whether to add the `.git` suffix or not.

### `stringify(obj, type)`
Stringifies a `GitUrl` object.

#### Params

- **GitUrl** `obj`: The parsed Git url object.
- **String** `type`: The type of the stringified url (default `obj.protocol`).

#### Return
- **String** The stringified url.














## :yum: How to contribute
Have an idea? Found a bug? See [how to contribute][contributing].


## :sparkling_heart: Support my projects
I open-source almost everything I can, and I try to reply to everyone needing help using these projects. Obviously,
this takes time. You can integrate and use these projects in your applications *for free*! You can even change the source code and redistribute (even resell it).

However, if you get some profit from this or just want to encourage me to continue creating stuff, there are few ways you can do it:


 - Starring and sharing the projects you like :rocket:
 - [![Buy me a book][badge_amazon]][amazon]—I love books! I will remember you after years if you buy me one. :grin: :book:
 - [![PayPal][badge_paypal]][paypal-donations]—You can make one-time donations via PayPal. I'll probably buy a ~~coffee~~ tea. :tea:
 - [![Support me on Patreon][badge_patreon]][patreon]—Set up a recurring monthly donation and you will get interesting news about what I'm doing (things that I don't share with everyone).
 - **Bitcoin**—You can send me bitcoins at this address (or scanning the code below): `1P9BRsmazNQcuyTxEqveUsnf5CERdq35V6`

    ![](https://i.imgur.com/z6OQI95.png)


Thanks! :heart:
















## :dizzy: Where is this library used?
If you are using this library in one of your projects, add it in this list. :sparkles:

 - `documentation`
 - `release-it`
 - `apollo`
 - `@atomist/automation-client`
 - `@storybook/storybook-deployer`
 - `@kadira/storybook-deployer`
 - `@atomist/automation-client-ext-raven`
 - `gatsby-source-git`
 - `umi-build-dev`
 - `git-source`
 - `@atomist/sdm-pack-analysis`
 - `@git-stack/server-core`
 - `@qiwi/semantic-release-gh-pages-plugin`
 - `@nuxt/telemetry`
 - `@lerna/github-client`
 - `@umijs/block-sdk`
 - `@instructure/ui-scripts`
 - `lambda-service`
 - `@wetrial/block-sdk`
 - `hzero-block-sdk`
 - `@micro-app/shared-utils`
 - `remax-stats`
 - `beachball`
 - `workspace-tools`
 - `gitbook-start-plugin-iaas-ull-es-noejaco2017`
 - `autorelease-setup`
 - `documentation-custom-markdown`
 - `@hygiene/plugin-github-url`
 - `sherry-utils`
 - `@unibtc/release-it`
 - `clipped`
 - `@erquhart/lerna-github-client`
 - `@0x-lerna-fork/github-client`
 - `common-boilerplate`
 - `@atomist/uhura`
 - `@brisk-docs/website`
 - `@hawkingnetwork/react-native-tab-view`
 - `miguelcostero-ng2-toasty`
 - `docula-ui`
 - `@brisk-docs/gatsby-generator`
 - `@microservices/cli`
 - `@atomist/cli`
 - `stylelint-formatter-utils`
 - `omg`
 - `sync-repos`
 - `@facadecompany/ignition-ui`
 - `@geut/git-url-parse`
 - `@temporg/rds-scripts`
 - `@git-stack/hemera-plugin`
 - `@yarnpkg/plugin-git`
 - `@koumoul/gh-pages-multi`
 - `@s-ui/mono`
 - `@feizheng/next-git-url`
 - `@xdn/cli`
 - `@adminide-stack/git-api-browser`
 - `semantic-release-gitmoji`
 - `committing`
 - `gitbook-start-https-alex-moi`
 - `gitbook-start-iaas-ull-es-merquililycony`
 - `proyecto-sytw-alex-moi`
 - `gitbook-start-iaas-ull-es-alex-moi`
 - `gitbook-start-iaas-bbdd-alex-moi`
 - `complan`
 - `@axetroy/git-clone`
 - `generator-cleanphp`
 - `@axetroy/gpmx`
 - `documentation-habitlab`
 - `nodeschool-admin`
 - `one-more-gitlab-cli`
 - `def-core`
 - `gd-cli`
 - `node-coverage-server`
 - `strapper`
 - `github-publish-npm`
 - `ogh`
 - `sinit`
 - `smart-clone`
 - `download-repo-cli`
 - `generator-nm-bti`
 - `gitc`
 - `gitline`
 - `gitlab-ci-variables-cli`
 - `gitlab-ci-variables-setter-cli`
 - `documentation-fork`
 - `@axetroy/gpm`
 - `generator-openapi-repo`
 - `git-url-promise`
 - `kef-core`
 - `@pvdlg/semantic-release`
 - `gitlab-tool-cli`
 - `snipx`
 - `yarn-upgrade-on-ci`
 - `@hjin/generator-app`
 - `@reframe/github-pages`
 - `belt-repo`
 - `@esops/publish-github-pages`
 - `@hugomrdias/documentation`
 - `just-dev-sdk`
 - `@activeviam/documentation`
 - `git-signed`
 - `cz-conventional-changelog-befe`
 - `@voodeng/archive`
 - `@voodeng/uppacks`
 - `create-apex-js-app`
 - `auto-changelog-vsts`
 - `harry-reporter`
 - `ssh-remote`
 - `@campus-online/gatsby-source-git`
 - `gtni`
 - `ci-yarn-upgrade`
 - `generator-clearphp`
 - `openapi-repo-generator`
 - `git-imitate`
 - `vscode-gpm`
 - `@atomist/ci-sdm`
 - `documentation42`
 - `@limejs/cli`
 - `lime-cli`
 - `laborious`
 - `release-it-http`
 - `bibi`
 - `lcov-server`
 - `create-release-it`
 - `git-service-node`
 - `@infinitecsolutions/storybook-deployer`
 - `@1nd/documentation`
 - `branch-release`
 - `git-cherry-fix`
 - `vuepress-plugin-remote-url`
 - `gatsby-source-github-raw`
 - `moto-connector`
 - `@zpmpkg/zpm`
 - `konitor`
 - `release2hub`
 - `@geut/git-compare-template`
 - `@geut/chan-parser`
 - `git-observer`
 - `docula-ui-express`
 - `sn-flutter-boot`
 - `spk`
 - `umi-plugin-repo`
 - `@epranka/create-tsx-package`
 - `flutter-boot`
 - `node-norman`
 - `remote-commit-url`
 - `air-material_cli`
 - `@belt/repo`
 - `@arcanis/sherlock`
 - `@dandean/storybook-deployer`
 - `git-upstream`
 - `@epranka/create-package`
 - `configorama`
 - `git-lab-cli`
 - `@cratosw/gatsby-antd`
 - `@pubcore/node-docker-build`
 - `@tjmonsi/generator-uplb-hci-lab-project-template`
 - `@tagoro9/git`
 - `tldw`
 - `gatsby-theme-hansin`
 - `aral-vps-test`
 - `generate-preview`
 - `@temporg/ui-scripts`
 - `bitbucket-pullr`
 - `canarist`
 - `@s-ui/changelog`
 - `@whey/gatsby-theme-whey`
 - `@docomodigital/pdor`
 - `auto-clone`
 - `create-sourcegraph-extension`
 - `@git-stack/module-server`
 - `@senti-techlabs/generator-senti-project-template`
 - `create-n`
 - `aral-server`
 - `gatsby-source-git-remotes`
 - `kit-command`
 - `git-push-pr`
 - `actions-package-update`
 - `@bcgov/gatsby-source-github-raw`
 - `@pagedip/tool-autorelease`
 - `documentation-markdown-themes`
 - `@theowenyoung/gatsby-source-git`
 - `@shopgate/pwa-releaser`
 - `@vicoders/cli2`
 - `@amorist/gatsby-theme-antd`
 - `@stavalfi/ci`
 - `cirodown`
 - `@apardellass/react-native-audio-stream`
 - `gatsby-theme-cone`
 - `changelog.md`
 - `wp-continuous-deployment`
 - `gatsby-source-npmjs`
 - `query-registry`
 - `l2forlerna`
 - `detect-node-support`
 - `@patrickhulce/scripts`
 - `@cilyn/bitbucket`
 - `@gasket/plugin-metrics`
 - `fotingo`
 - `mira`
 - `react-native-plugpag-wrapper`
 - `meta-release`
 - `@cyber-tools/lib-cli`
 - `@feizheng/git-url-cli`
 - `@s-ui/ssr`
 - `@myetherwallet/mew-components`
 - `ship-release`
 - `@hnp/package-scripts`
 - `@antv/gatsby-theme-antv`
 - `git-csv`
 - `dx-scanner`
 - `rollman`
 - `@backstage/plugin-scaffolder-backend`
 - `@tahini/nc`
 - `lage`
 - `pr-log`
 - `git-issues`











## :scroll: License

[MIT][license] © [Ionică Bizău][website]






[license]: /LICENSE
[website]: https://ionicabizau.net
[contributing]: /CONTRIBUTING.md
[docs]: /DOCUMENTATION.md
[badge_patreon]: https://ionicabizau.github.io/badges/patreon.svg
[badge_amazon]: https://ionicabizau.github.io/badges/amazon.svg
[badge_paypal]: https://ionicabizau.github.io/badges/paypal.svg
[badge_paypal_donate]: https://ionicabizau.github.io/badges/paypal_donate.svg
[patreon]: https://www.patreon.com/ionicabizau
[amazon]: http://amzn.eu/hRo9sIZ
[paypal-donations]: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=RVXDDLKKLQRJW
