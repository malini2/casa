# CASA Project and Organization Overview

[![rspec](https://github.com/rubyforgood/casa/workflows/rspec/badge.svg)](https://github.com/rubyforgood/casa/actions/workflows/rspec.yml)
[![cypress](https://github.com/rubyforgood/casa/workflows/cypress/badge.svg)](https://github.com/rubyforgood/casa/actions/workflows/cypress.yml)
[![erb lint](https://github.com/rubyforgood/casa/actions/workflows/erb_lint.yml/badge.svg)](https://github.com/rubyforgood/casa/actions/workflows/erb_lint.yml)
[![standardrb lint](https://github.com/rubyforgood/casa/actions/workflows/ruby_lint.yml/badge.svg)](https://github.com/rubyforgood/casa/actions/workflows/ruby_lint.yml)
[![brakeman](https://github.com/rubyforgood/casa/workflows/brakeman/badge.svg)](https://github.com/rubyforgood/casa/actions/workflows/security.yml)
[![yarn lint](https://github.com/rubyforgood/casa/actions/workflows/yarn_lint.yml/badge.svg)](https://github.com/rubyforgood/casa/actions/workflows/yarn_lint.yml)

[![Maintainability](https://api.codeclimate.com/v1/badges/24f3bb10db6afac417e2/maintainability)](https://codeclimate.com/github/rubyforgood/casa/trends/technical_debt)
[![Test Coverage](https://api.codeclimate.com/v1/badges/24f3bb10db6afac417e2/test_coverage)](https://codeclimate.com/github/rubyforgood/casa/trends/test_coverage_total)
[![Snyk Vulnerabilities](https://snyk.io/test/github/rubyforgood/casa/badge.svg)](https://snyk.io/test/github/rubyforgood/casa)
[![Average time to resolve an issue](http://isitmaintained.com/badge/resolution/rubyforgood/casa.svg)](http://isitmaintained.com/project/rubyforgood/casa "Average time to resolve an issue")

[![View performance data on Skylight](https://badges.skylight.io/status/tFh7xrs3Qnaf.svg?token=1C-Q7p8jEFlG7t69Yl5DaJwa-ipWI8gLw9wLJf53xmQ)](https://www.skylight.io/app/applications/tFh7xrs3Qnaf)
[![View performance data on Skylight](https://badges.skylight.io/problem/tFh7xrs3Qnaf.svg?token=1C-Q7p8jEFlG7t69Yl5DaJwa-ipWI8gLw9wLJf53xmQ)](https://www.skylight.io/app/applications/tFh7xrs3Qnaf)
[![View performance data on Skylight](https://badges.skylight.io/typical/tFh7xrs3Qnaf.svg?token=1C-Q7p8jEFlG7t69Yl5DaJwa-ipWI8gLw9wLJf53xmQ)](https://www.skylight.io/app/applications/tFh7xrs3Qnaf)
[![View performance data on Skylight](https://badges.skylight.io/rpm/tFh7xrs3Qnaf.svg?token=1C-Q7p8jEFlG7t69Yl5DaJwa-ipWI8gLw9wLJf53xmQ)](https://www.skylight.io/app/applications/tFh7xrs3Qnaf)

CASA (Court Appointed Special Advocate) is a role fulfilled by a trained volunteer sworn into a county-level juvenile dependency court system to advocate on behalf of a youth in the corresponding county's foster care system. CASA is also the namesake role of the national organization, CASA, which exists to cultivate and supervise volunteers carrying out this work – with county level chapters (operating relatively independently of each other) across the country.

<!-- toc -->

- [Welcome contributors!](#welcome-contributors)
  - [About this project](#about-this-project)
- [Developing! ✨🛠✨](#developing-)
  - [Installation](#installation)
    - [General Setup Instructions](#general-setup-instructions)
    - [Platform Specific Installation Instructions](#platform-specific-installation-instructions)
      - [Ubuntu and WSL](#ubuntu-and-wsl)
  - [Running the App / Verifying Installation](#running-the-app--verifying-installation)
- [Other Documentation](#other-documentation)
    - [Common issues](#common-issues)
- [Communication and Collaboration](#communication-and-collaboration)
- [History](#history)

<!-- tocstop -->

## Welcome contributors!

We are very happy to have you! CASA and Ruby for Good are committed to welcoming new contrinbutors of all skill levels.

We highly recommend that you join us in slack https://rubyforgood.herokuapp.com/ #casa channel to ask questions quickly and hear about office hours (currently Wednesday 6-8pm Pacific), stakeholder news, and upcoming new issues.

Issues on the issue board https://github.com/rubyforgood/casa/projects/1 in the TODO column are fair game. An issue can be claimed by commenting on it.

Pull requests which are not for an issue but which improve the codebase are also welcome! Feel free to make github issues for bugs and improvements. A maintainer will be keeping an eye on issues and PRs every day or three.

See also our [contributing guide](./doc/CONTRIBUTING.md) 💖 ✨

### About this project

CASA is a national organization with many regional chapters. We currenly work with [Prince George's County CASA in Maryland](https://pgcasa.org/) and [Montgomery CASA Maryland](https://casaspeaks4kids.com)

This system provides value by:

- providing volunteers with a portal for logging activity
- allow supervisors to oversee volunteer activity
- generate reports on volunteer activity for admins to use in grant proposals

Read about the [product sense](doc/productsense.md) that guides our approach to this work.

**How CASA works:**

- A foster youth is represented as a **CASA case**.
- The **CASA case** is assigned to a **volunteer**.
- The **volunteer** records their efforts spent on the CASA case as **case contacts**.
- **Supervisors** oversee CASA **volunteers** by monitoring, tracking, and advising them on **CASA case** activities.
- At PG CASA, the minimum volunteer commitment is one year (this varies by CASA chapter, in San Francisco the minimum commitment is ~ two years).  A volunteer's  lifecycle is very long, so there's a lot of activity for chapters to organize.

**Project Considerations**

- PG CASA is operating under a very tight budget. Right now, they manually input volunteer data into [a volunteer management software built specifically for CASA](http://www.simplyoptima.com/), but upgrading their account for multiple user licenses to allow volunteers to self-log activity data is beyond their budget. Hence why we are building as lightweight a solution as possible that can sustain itself with Ruby for Good's support.
- While the scope of this platform's use is currently for PG County CASA and Montgomery county CASA, we are building with a mind toward multitenancy so this platform could prospectively be used by other CASA chapters across the country.

**More information:**

The complete [role description of a CASA volunteer](https://pgcasa.org/volunteer-description/) in Prince George's County.

# Developing! ✨🛠✨
## Installation
### General Setup Instructions  
**Ruby**  
1. Install a ruby version manager: [rvm](https://rvm.io/) or [rbenv](https://github.com/rbenv/rbenv)
1. when you cd into the project directory, let your version manager install the ruby version in `.ruby-version`. Right now that's Ruby 3.0.1
1. `gem install bundler`

**node.js**  
1. (Recommended) Install [nvm](https://github.com/nvm-sh/nvm#installing-and-updating), which is a **n**ode **v**ersion **m**anager.
1. Install a current LTS version of Node. 12.16.2 works.
1. Install [yarn](https://classic.yarnpkg.com/en/docs/install). On Ubuntu, [make sure you install it from the official Yarn repo instead of cmdtest](https://classic.yarnpkg.com/en/docs/install/#debian-stable).

**PostgreSQL ("postgres")**  
1. Make sure that postgres is installed.  
  - If you're on Ubuntu/WSL, use `sudo apt-get install libpq-dev` so the gem can install. [Use the Postgres repo for Ubuntu or WSL to get the server and client tools](https://www.postgresql.org/download/linux/ubuntu/).
  - If you're on Fedora/Cent Os use `sudo dnf install libpq-devel`. [If you prefer choose package of libpq-devel via rpm](https://pkgs.org/download/libpq-devel)
  - If you're on Windows, use the official [installer](https://www.postgresql.org/download/windows/) and accept all defaults.  Alternatively, a [Chocolatey](https://chocolatey.org/packages/postgresql) package is available with `choco install postgresql`.

**Chrome Browser**

1. The Spec tests uses Chrome Browser and Chromedriver for some of the tests. A current version of chromedriver will be installed when `bundle install` is run. TO install Chrome, see [Chrome Install](https://support.google.com/chrome/answer/95346?hl=en&ref_topic=7439538).

Another option is to install the Chromium browser for your operating system so the browser-based Ruby feature/integration tests can run. Installing `chromium-browser` is enough, even in WSL (Windows subsystem for Linux)

**Downloading the Project**  
(*on a Mac or Linux machine*)
1. `git clone https://github.com/rubyforgood/casa.git` clone the repo to your local machine. You should create a fork in GitHub if you don't have permission to commit directly to this repo, though. See [our contributing guide](doc/CONTRIBUTING.md) for more detailed instructions.

**Installing Packages**  
1. `cd casa/`
1. `bundle install` install ruby dependencies.
1. `yarn install` install javascript dependencies.

**Database Setup**
1. `bin/rails db:setup` create schema
    requires running local postgres, with a role created for whatever user you're running rails as
1. `bin/rails db:seed:replant` generates test data (can be rerun to regenerate test data)

### Platform Specific Installation Instructions
 - [Docker](doc/DOCKER.md)
 - [Linux](doc/LINUX_SETUP.md)
 - [Mac(Help Wanted)](doc/MAC_SETUP.md)
 - Windows(Help Wanted)
 - Windows Subsystem for Linux(WSL) (Help Wanted)

#### Ubuntu and WSL

1. If you are on Ubuntu in Windows Subsystem for Linux (WSL) and `rbenv install` indicates that the Ruby version is unavailable, you might be using Ubuntu's default install of `ruby-build`, which only comes with old installs of Ruby (ending before 2.6.) You should uninstall rvm and ruby-build's apt packages (`apt remove rvm ruby-build`) and install them with Git like this:

- `git clone https://github.com/rbenv/rbenv.git ~/.rbenv`
- `echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc`
- `echo 'eval "$(rbenv init -)"' >> ~/.bashrc`
- `exec $SHELL`
- `git clone https://github.com/rbenv/ruby-build.git "$(rbenv root)"/plugins/ruby-build`

You'll probably hit a problem where ruby-version reads `ruby-2.7.2` but the install available to you is called `2.7.2`. If you do, install [rbenv-alias](https://github.com/tpope/rbenv-aliases) and create an alias between the two.

### Common issues

1. If your rails/rake commands hang forever instead of running, try: `rails app:update:bin`
1. There is currently no option for a user to sign up and create an account through the UI. This is intentional. If you want to log in, use a pre-seeded user account and its credentials.
1. If you are on windows and see the error "Requirements support for mingw is not implemented yet" then use https://rubyinstaller.org/ instead

## Running the App / Verifying Installation
1. `bin/rails server` or `bin/rails s` to start the local webserver

**Running Tests**  
 - run the ruby test suite `bin/rails spec`  
 - run the javascript test suite `yarn test`   
 - run cypress tests  

       bundle exec rails server -b 0.0.0.0 -p 4040
       npm run test:cypress --exit-code 0


If you have trouble running tests, check out CI scripts in [`.github/workflows/`](.github/workflows/) for sample commands.  
Test coverage is run by simplecov on all builds and aggregated by CodeClimate

**Cleaning up before you pull request**  
1. `bundle exec standardrb --fix` auto-fix Ruby linting issues [more linter info](https://github.com/testdouble/standard)
1. `bundle exec erblint --lint-all --autocorrect` [ERB linter](https://github.com/Shopify/erb-lint)
1. `yarn lint:fix` to run the [JS linter](https://standardjs.com/index.html) and fix isses
1. `rake factory_bot:lint` if you have been editing factories and want to find factories and traits which produce invalid objects

If additional work arises from your pull request that is outside the scope of the issue it resolves, please open a new issue.

**Local email**

We are using [Letter Opener](https://github.com/ryanb/letter_opener) in
development to receive mail. All emails sent in development should open in a
new tab in the browser.

To see local email previews, check out http://localhost:3000/rails/mailers

**Post-deployment tasks**

We are using [After Party](https://github.com/theSteveMitchell/after_party) to
run post-deployment tasks. These tasks may include one-time necessary updates to the
database. Run the tasks manually by:  
```
bundle exec rake after_party:run
```

Alternatively, every time you pull the main branch, run:  
```
bin/update
```

which will run any database migrations, update gems and yarn packages, and run
the after party post-deployment tasks.

# Other Documentation  
Check out [the wiki](https://github.com/rubyforgood/casa/wiki)  
  
There is a `doc` directory at the top level that includes:
* an `architecture-decisions` directory containing important architectural decisions and entity relationship diagrams of various models
  (see the article [Architectural Decision Records](http://thinkrelevance.com/blog/2011/11/15/documenting-architecture-decisions) describing this approach).
* [Code of Conduct](doc/code-of-conduct.md)
* [CYPRESS.md](doc/CYPRESS.md)
* [productsense.md](doc/productsense.md)(for team leads & product interested contributors)
* [SECURITY.md](doc/SECURITY.md)

# Communication and Collaboration

Most conversation happens in the #casa channel of the Ruby For Good slack. Get access here: https://rubyforgood.herokuapp.com/

You can also open an issue or comment on an issue on github and a maintainer will reply to you.

We have a weekly team office hours / hangout on Wednesday 6-8pm Pacific time where we do pair/mob programming and talk about issues. Please stop by!

We have a weekly stakeholder call with PG CASA staff on Wednesday at 8:30am Pacific time where we show off progress and discuss launch plans. Feel free to join!

Join info for all public meetings is posted in the rubyforgood slack in the #casa channel

# History

First CASA supervisor training: 12 August 2020 🎉
