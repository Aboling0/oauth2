<p align="center">
    <a href="http://oauth.net/2/" target="_blank" rel="noopener">
      <img src="https://github.com/oauth-xx/oauth2/raw/main/docs/images/logo/oauth2-logo-124px.png?raw=true" alt="OAuth 2.0 Logo by Chris Messina, CC BY-SA 3.0">
    </a>
    <a href="https://www.ruby-lang.org/" target="_blank" rel="noopener">
      <img width="124px" src="https://github.com/oauth-xx/oauth2/raw/main/docs/images/logo/ruby-logo-198px.svg?raw=true" alt="Yukihiro Matsumoto, Ruby Visual Identity Team, CC BY-SA 2.5">
    </a>
</p>

## OAuth2

[![Version][👽versioni]][👽version]
[![License: MIT][📄license-img]][📄license-ref]
[![Downloads Rank][👽dl-ranki]][👽dl-rank]
[![Open Source Helpers][👽oss-helpi]][👽oss-help]
[![Depfu][🔑depfui♻️]][🔑depfu]
[![CodeCov Test Coverage][🔑codecovi♻️]][🔑codecov]
[![Coveralls Test Coverage][🔑coveralls-img]][🔑coveralls]
[![CodeClimate Test Coverage][🔑cc-covi♻️]][🔑cc-cov]
[![Maintainability][🔑cc-mnti♻️]][🔑cc-mnt]
[![CI Heads][🚎3-hd-wfi]][🚎3-hd-wf]
[![CI Current][🚎11-c-wfi]][🚎11-c-wf]
[![CI Truffle Ruby][🚎9-t-wfi]][🚎9-t-wf]
[![CI JRuby][🚎10-j-wfi]][🚎10-j-wf]
[![CI Supported][🚎6-s-wfi]][🚎6-s-wf]
[![CI Legacy][🚎4-lg-wfi]][🚎4-lg-wf]
[![CI Unsupported][🚎7-us-wfi]][🚎7-us-wf]
[![CI Ancient][🚎1-an-wfi]][🚎1-an-wf]
[![CI Test Coverage][🚎2-cov-wfi]][🚎2-cov-wf]
[![CI Style][🚎5-st-wfi]][🚎5-st-wf]

---

[![Liberapay Patrons][⛳liberapay-img]][⛳liberapay]
[![Sponsor Me on Github][🖇sponsor-img]][🖇sponsor]
[![Buy me a coffee][🖇buyme-small-img]][🖇buyme]
[![Donate on Polar][🖇polar-img]][🖇polar]
[![Donate to my FLOSS or refugee efforts at ko-fi.com][🖇kofi-img]][🖇kofi]
[![Donate to my FLOSS or refugee efforts using Patreon][🖇patreon-img]][🖇patreon]

OAuth 2.0 is the industry-standard protocol for authorization.
OAuth 2.0 focuses on client developer simplicity while providing specific authorization flows for web applications,
    desktop applications, mobile phones, and living room devices.
This is a RubyGem for implementing OAuth 2.0 clients (not servers) in Ruby applications.

Quick example: Convert the following `curl` command into a token request using this gem...

```shell
curl --request POST \
  --url 'https://login.microsoftonline.com/REDMOND_REDACTED/oauth2/token' \
  --header 'content-type: application/x-www-form-urlencoded' \
  --data grant_type=client_credentials \
  --data client_id=REDMOND_CLIENT_ID \
  --data client_secret=REDMOND_CLIENT_SECRET \
  --data resource=REDMOND_RESOURCE_UUID
```

NOTE: In the ruby version, certain params go in the get_token call, rather than in the client creation.

```ruby
OAuth2::Client.new(
  "REDMOND_CLIENT_ID", # client_id
  "REDMOND_CLIENT_SECRET", # client_secret
  auth_scheme: :request_body, # Other modes are supported: :basic_auth, :tls_client_auth, :private_key_jwt
  token_url: "oauth2/token", # relative path, except with leading `/`, then absolute path
  site: "https://login.microsoftonline.com/REDMOND_REDACTED",
). # The base path for token_url when it is relative
  client_credentials. # There are many other types to choose from!
  get_token(resource: "REDMOND_RESOURCE_UUID")
```

NOTE: `header` - The content type specified in the `curl` is already the default!

## 💡 Info you can shake a stick at

* [OAuth 2.0 Spec][oauth2-spec]
* [doorkeeper gem][doorkeeper-gem] for OAuth 2.0 server/provider implementation.
* [oauth sibling gem][sibling-gem] for OAuth 1.0 implementations in Ruby.

[oauth2-spec]: https://oauth.net/2/
[sibling-gem]: https://gitlab.com/oauth-xx/oauth
[doorkeeper-gem]: https://github.com/doorkeeper-gem/doorkeeper

| Tokens to Remember      | [![Gem name][⛳️name-img]][⛳️gem-name] [![Gem namespace][⛳️namespace-img]][⛳️gem-namespace]                                                                                                                                                                                                                                                                                                                                                                                            |
|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Works with JRuby        | [![JRuby 9.2 Compat][💎jruby-9.2i]][🚎10-j-wf] [![JRuby 9.3 Compat][💎jruby-9.3i]][🚎10-j-wf] [![JRuby 9.4 Compat][💎jruby-9.4i]][🚎10-j-wf] [![JRuby 10.0 Compat][💎jruby-c-i]][🚎11-c-wf] [![JRuby HEAD Compat][💎jruby-headi]][🚎3-hd-wf]                                                                                                                                                                                           |
| Works with Truffle Ruby | [![Truffle Ruby 23.1 Compat][💎truby-23.1i]][🚎9-t-wf] [![Truffle Ruby 24.1 Compat][💎truby-c-i]][🚎11-c-wf] [![Truffle Ruby HEAD Compat][💎truby-headi]][🚎3-hd-wf]                                                                                                                                                                                                    |
| Works with MRI Ruby 3   | [![Ruby 3.0 Compat][💎ruby-3.0i]][🚎4-lg-wf] [![Ruby 3.1 Compat][💎ruby-3.1i]][🚎6-s-wf] [![Ruby 3.2 Compat][💎ruby-3.2i]][🚎6-s-wf] [![Ruby 3.3 Compat][💎ruby-3.3i]][🚎6-s-wf] [![Ruby 3.4 Compat][💎ruby-c-i]][🚎11-c-wf] [![Ruby HEAD Compat][💎ruby-headi]][🚎3-hd-wf]                                                                                                                                                                                                           |
| Works with MRI Ruby 2   | [![Ruby 2.3 Compat][💎ruby-2.3i]][🚎1-an-wf] [![Ruby 2.4 Compat][💎ruby-2.4i]][🚎1-an-wf] [![Ruby 2.5 Compat][💎ruby-2.5i]][🚎1-an-wf] [![Ruby 2.6 Compat][💎ruby-2.6i]][🚎7-us-wf] [![Ruby 2.7 Compat][💎ruby-2.7i]][🚎7-us-wf]                                                                                                                                                                                                                                                      |
| Source                  | [![Source on GitLab.com][📜src-gl-img]][📜src-gl] [![Source on CodeBerg.org][📜src-cb-img]][📜src-cb] [![Source on Github.com][📜src-gh-img]][📜src-gh] [![The best SHA: dQw4w9WgXcQ!][🧮kloc-img]][🧮kloc]                                                                                                                                                                                                                                                                           |
| Documentation           | [![Discussion][⛳gg-discussions-img]][⛳gg-discussions] [![Current release on RubyDoc.info][📜docs-cr-rd-img]][🚎yard-current] [![HEAD on RubyDoc.info][📜docs-head-rd-img]][🚎yard-head] [![BDFL Blog][🚂bdfl-blog-img]][🚂bdfl-blog] [![Wiki][📜wiki-img]][📜wiki]                                                                                                                                                                                                                    |
| Compliance              | [![License: MIT][📄license-img]][📄license-ref] [![📄ilo-declaration-img]][📄ilo-declaration] [![Security Policy][🔐security-img]][🔐security] [![Enforced Code Style][💎rlts-img]][💎rlts] [![CodeQL][🖐codeQL-img]][🖐codeQL] [![Contributor Covenant 2.1][🪇conduct-img]][🪇conduct] [![SemVer 2.0.0][📌semver-img]][📌semver] [![Keep-A-Changelog 1.0.0][📗keep-changelog-img]][📗keep-changelog] [![Gitmoji Commits][📌gitmoji-img]][📌gitmoji] [![FOSSA][🏘fossa-img]][🏘fossa] |
| Expert 1:1 Support      | [![Get help from me on Upwork][👨🏼‍🏫expsup-upwork-img]][👨🏼‍🏫expsup-upwork] `or` [![Get help from me on Codementor][👨🏼‍🏫expsup-codementor-img]][👨🏼‍🏫expsup-codementor]                                                                                                                                                                                                                                                                                                      |
| Enterprise Support      | [![Get help from me on Tidelift][🏙️entsup-tidelift-img]][🏙️entsup-tidelift]<br/>💡Subscribe for support guarantees covering _all_ FLOSS dependencies!<br/>💡Tidelift is part of [Sonar][🏙️entsup-tidelift-sonar]!<br/>💡Tidelift pays maintainers to maintain the software you depend on!<br/>📊`@`Pointy Haired Boss: An [enterprise support][🏙️entsup-tidelift] subscription is "[never gonna let you down][🧮kloc]", and *supports* open source maintainers!                   |
| Comrade BDFL 🎖️        | [![Follow Me on LinkedIn][💖🖇linkedin-img]][💖🖇linkedin] [![Follow Me on Ruby.Social][💖🐘ruby-mast-img]][💖🐘ruby-mast] [![Follow Me on Bluesky][💖🦋bluesky-img]][💖🦋bluesky] [![Contact BDFL][🚂bdfl-contact-img]][🚂bdfl-contact] [![My technical writing][💖💁🏼‍♂️devto-img]][💖💁🏼‍♂️devto]                                                                                                                                                                                |
| `...` 💖                | [![Find Me on WellFound:][💖✌️wellfound-img]][💖✌️wellfound] [![Find Me on CrunchBase][💖💲crunchbase-img]][💖💲crunchbase] [![My LinkTree][💖🌳linktree-img]][💖🌳linktree] [![More About Me][💖💁🏼‍♂️aboutme-img]][💖💁🏼‍♂️aboutme] [🧊][💖🧊berg] [🐙][💖🐙hub]  [🛖][💖🛖hut] [🧪][💖🧪lab]                                                                                                                                                                                     |

## 🚀 Release Documentation

### Version 2.0.x

<details>
  <summary>2.0.x Readmes</summary>

| Version | Release Date | Readme                                                      |
|---------|--------------|-------------------------------------------------------------|
| 2.0.10  | 2025-05-16   | https://gitlab.com/oauth-xx/oauth2/-/blob/v2.0.10/README.md |
| 2.0.9   | 2022-09-16   | https://gitlab.com/oauth-xx/oauth2/-/blob/v2.0.9/README.md  |
| 2.0.8   | 2022-09-01   | https://gitlab.com/oauth-xx/oauth2/-/blob/v2.0.8/README.md  |
| 2.0.7   | 2022-08-22   | https://gitlab.com/oauth-xx/oauth2/-/blob/v2.0.7/README.md  |
| 2.0.6   | 2022-07-13   | https://gitlab.com/oauth-xx/oauth2/-/blob/v2.0.6/README.md  |
| 2.0.5   | 2022-07-07   | https://gitlab.com/oauth-xx/oauth2/-/blob/v2.0.5/README.md  |
| 2.0.4   | 2022-07-01   | https://gitlab.com/oauth-xx/oauth2/-/blob/v2.0.4/README.md  |
| 2.0.3   | 2022-06-28   | https://gitlab.com/oauth-xx/oauth2/-/blob/v2.0.3/README.md  |
| 2.0.2   | 2022-06-24   | https://gitlab.com/oauth-xx/oauth2/-/blob/v2.0.2/README.md  |
| 2.0.1   | 2022-06-22   | https://gitlab.com/oauth-xx/oauth2/-/blob/v2.0.1/README.md  |
| 2.0.0   | 2022-06-21   | https://gitlab.com/oauth-xx/oauth2/-/blob/v2.0.0/README.md  |
</details>

### Older Releases

<details>
  <summary>1.4.x Readmes</summary>

| Version | Release Date | Readme                                                      |
|---------|--------------|-------------------------------------------------------------|
| 1.4.11  | Sep 16, 2022 | https://gitlab.com/oauth-xx/oauth2/-/blob/v1.4.11/README.md |
| 1.4.10  | Jul 1, 2022  | https://gitlab.com/oauth-xx/oauth2/-/blob/v1.4.10/README.md |
| 1.4.9   | Feb 20, 2022 | https://gitlab.com/oauth-xx/oauth2/-/blob/v1.4.9/README.md  |
| 1.4.8   | Feb 18, 2022 | https://gitlab.com/oauth-xx/oauth2/-/blob/v1.4.8/README.md  |
| 1.4.7   | Mar 19, 2021 | https://gitlab.com/oauth-xx/oauth2/-/blob/v1.4.7/README.md  |
| 1.4.6   | Mar 19, 2021 | https://gitlab.com/oauth-xx/oauth2/-/blob/v1.4.6/README.md  |
| 1.4.5   | Mar 18, 2021 | https://gitlab.com/oauth-xx/oauth2/-/blob/v1.4.5/README.md  |
| 1.4.4   | Feb 12, 2020 | https://gitlab.com/oauth-xx/oauth2/-/blob/v1.4.4/README.md  |
| 1.4.3   | Jan 29, 2020 | https://gitlab.com/oauth-xx/oauth2/-/blob/v1.4.3/README.md  |
| 1.4.2   | Oct 1, 2019  | https://gitlab.com/oauth-xx/oauth2/-/blob/v1.4.2/README.md  |
| 1.4.1   | Oct 13, 2018 | https://gitlab.com/oauth-xx/oauth2/-/blob/v1.4.1/README.md  |
| 1.4.0   | Jun 9, 2017  | https://gitlab.com/oauth-xx/oauth2/-/blob/v1.4.0/README.md  |
</details>

<details>
  <summary>1.3.x Readmes</summary>

| Version  | Release Date | Readme                                                   |
|----------|--------------|----------------------------------------------------------|
| 1.3.1    | Mar 3, 2017  | https://gitlab.com/oauth-xx/oauth2/-/blob/v1.3.1/README.md |
| 1.3.0    | Dec 27, 2016 | https://gitlab.com/oauth-xx/oauth2/-/blob/v1.3.0/README.md |
</details>

<details>
  <summary>&le;= 1.2.x Readmes (2016 and before)</summary>

| Version  | Release Date | Readme                                                   |
|----------|--------------|----------------------------------------------------------|
| 1.2.0    | Jun 30, 2016 | https://gitlab.com/oauth-xx/oauth2/-/blob/v1.2.0/README.md |
| 1.1.0    | Jan 30, 2016 | https://gitlab.com/oauth-xx/oauth2/-/blob/v1.1.0/README.md |
| 1.0.0    | May 23, 2014 | https://gitlab.com/oauth-xx/oauth2/-/blob/v1.0.0/README.md |
| < 1.0.0  | Find here    | https://gitlab.com/oauth-xx/oauth2/-/tags                  |
</details>

## ✨ Installation

Install the gem and add to the application's Gemfile by executing:

    $ bundle add oauth2

If bundler is not being used to manage dependencies, install the gem by executing:

    $ gem install oauth2

### 🔒 Secure Installation

`oauth2` is cryptographically signed, and has verifiable [SHA-256 and SHA-512][💎SHA_checksums] checksums by
[stone_checksums][💎stone_checksums]. Be sure the gem you install hasn’t been tampered with
by following the instructions below.

Add my public key (if you haven’t already, expires 2045-04-29) as a trusted certificate:

```shell
gem cert --add <(curl -Ls https://raw.github.com/kettle-rb/oauth2/main/certs/pboling.pem)
```

You only need to do that once.  Then proceed to install with:

```shell
gem install oauth2 -P MediumSecurity
```

The `MediumSecurity` trust profile will verify signed gems, but allow the installation of unsigned dependencies.

This is necessary because not all of `oauth2`’s dependencies are signed, so we cannot use `HighSecurity`.

If you want to up your security game full-time:

```shell
bundle config set --global trust-policy MediumSecurity
```

NOTE: Be prepared to track down certs for signed gems and add them the same way you added mine.

## OAuth2 for Enterprise

Available as part of the Tidelift Subscription.

The maintainers of OAuth2 and thousands of other packages are working with Tidelift to deliver commercial support and maintenance for the open source packages you use to build your applications. Save time, reduce risk, and improve code health, while paying the maintainers of the exact packages you use. [Learn more.][tidelift-ref]

[tidelift-ref]: https://tidelift.com/subscription/pkg/rubygems-oauth2?utm_source=rubygems-oauth2&utm_medium=referral&utm_campaign=enterprise

## Security contact information

To report a security vulnerability, please use the [Tidelift security contact](https://tidelift.com/security).
Tidelift will coordinate the fix and disclosure.

For more see [SECURITY.md][🔐security].

## What is new for v2.0?

- Officially support Ruby versions >= 2.7
- Unofficially support Ruby versions >= 2.5
- Incidentally support Ruby versions >= 2.2
- Drop support for the expired MAC Draft (all versions)
- Support IETF rfc7523 JWT Bearer Tokens
- Support IETF rfc7231 Relative Location in Redirect
- Support IETF rfc6749 Don't set oauth params when nil
- Support [OIDC 1.0 Private Key JWT](https://openid.net/specs/openid-connect-core-1_0.html#ClientAuthentication); based on the OAuth JWT assertion specification [(RFC 7523)](https://tools.ietf.org/html/rfc7523)
- Support new formats, including from [jsonapi.org](http://jsonapi.org/format/): `application/vdn.api+json`, `application/vnd.collection+json`, `application/hal+json`, `application/problem+json`
- Adds new option to `OAuth2::Client#get_token`:
    - `:access_token_class` (`AccessToken`); user specified class to use for all calls to `get_token`
- Adds new option to `OAuth2::AccessToken#initialize`:
    - `:expires_latency` (`nil`); number of seconds by which AccessToken validity will be reduced to offset latency
- By default, keys are transformed to snake case.
  - Original keys will still work as previously, in most scenarios, thanks to `rash_alt` gem.
  - However, this is a _breaking_ change if you rely on `response.parsed.to_h` to retain the original case, and the original wasn't snake case, as the keys in the result will be snake case.
  - As of version 2.0.4 you can turn key transformation off with the `snaky: false` option.
- By default, the `:auth_scheme` is now `:basic_auth` (instead of `:request_body`)
  - Third-party strategies and gems may need to be updated if a provider was requiring client id/secret in the request body
- [... A lot more](https://gitlab.com/oauth-xx/oauth2/-/blob/main/CHANGELOG.md#200-2022-06-21-tag)

## Compatibility

Targeted ruby compatibility is non-EOL versions of Ruby, currently 3.2, 3.3, and 3.4.
Compatibility is further distinguished as "Best Effort Support" or "Incidental Support" for older versions of Ruby.
This gem will install on Ruby versions >= v2.2 for 2.x releases.
See `1-4-stable` branch for older rubies.

<details>
  <summary>Ruby Engine Compatibility Policy</summary>

This gem is tested against MRI, JRuby, and Truffleruby.
Each of those has varying versions that target a specific version of MRI Ruby.
This gem should work in the just-listed Ruby engines according to the targeted MRI compatibility in the table below.
If you would like to add support for additional engines,
  see `gemfiles/README.md`, then submit a PR to the correct maintenance branch as according to the table below.
</details>

<details>
  <summary>Ruby Version Compatibility Policy</summary>

If something doesn't work on one of these interpreters, it's a bug.

This library may inadvertently work (or seem to work) on other Ruby
implementations, however support will only be provided for the versions listed
above.

If you would like this library to support another Ruby version, you may
volunteer to be a maintainer. Being a maintainer entails making sure all tests
run and pass on that implementation. When something breaks on your
implementation, you will be responsible for providing patches in a timely
fashion. If critical issues for a particular implementation exist at the time
of a major release, support for that Ruby version may be dropped.
</details>

|     | Ruby OAuth2 Version | Maintenance Branch | Targeted Support     | Best Effort Support     | Incidental Support           |
|:----|---------------------|--------------------|----------------------|-------------------------|------------------------------|
| 1️⃣ | 2.0.x               | `main`             | 3.2, 3.3, 3.4        | 2.5, 2.6, 2.7, 3.0, 3.1 | 2.2, 2.3, 2.4                |
| 2️⃣ | 1.4.x               | `1-4-stable`       | 3.2, 3.3, 3.4        | 2.5, 2.6, 2.7, 3.0, 3.1 | 1.9, 2.0, 2.1, 2.2, 2.3, 2.4 |
| 3️⃣ | older               | N/A                | Best of luck to you! | Please upgrade!         |                              |

NOTE: The 1.4 series will only receive critical security updates.
See [SECURITY.md][🚎sec-pol]

## Usage Examples

### Global Configuration

If you started seeing this warning, but everything is working fine, you can now silence it.
```log
OAuth2::AccessToken.from_hash: `hash` contained more than one 'token' key
```

```ruby
OAuth2.configure do |config|
  config.silence_extra_tokens_warning = true # default: false
  config.silence_no_tokens_warning = true # default: false, if you want to also silence warnings about no tokens
end
```

This comes from ambiguity in the spec about which token is the right token.
Some OAuth 2.0 standards legitimately have multiple tokens.
You may need to subclass `OAuth2::AccessToken`, or write your own custom alternative to it, and pass it in.
Specify your custom class with the `access_token_class` option.

If you only need one token you can, as of v2.0.10,
specify the exact token name you want to extract via the `OAuth2::AccessToken` using
the `token_name` option.

You'll likely need to do some source diving.
This gem has 100% test coverage for lines and branches, so the specs are a great place to look for ideas.
If you have time and energy please contribute to the documentation!

### `authorize_url` and `token_url` are on site root (Just Works!)

```ruby
require "oauth2"
client = OAuth2::Client.new("client_id", "client_secret", site: "https://example.org")
# => #<OAuth2::Client:0x00000001204c8288 @id="client_id", @secret="client_sec...
client.auth_code.authorize_url(redirect_uri: "http://localhost:8080/oauth2/callback")
# => "https://example.org/oauth/authorize?client_id=client_id&redirect_uri=http%3A%2F%2Flocalhost%3A8080%2Foauth2%2Fcallback&response_type=code"

access = client.auth_code.get_token("authorization_code_value", redirect_uri: "http://localhost:8080/oauth2/callback", headers: {"Authorization" => "Basic some_password"})
response = access.get("/api/resource", params: {"query_foo" => "bar"})
response.class.name
# => OAuth2::Response
```

### Relative `authorize_url` and `token_url` (Not on site root, Just Works!)

In above example, the default Authorization URL is `oauth/authorize` and default Access Token URL is `oauth/token`, and, as they are missing a leading `/`, both are relative.

```ruby
client = OAuth2::Client.new("client_id", "client_secret", site: "https://example.org/nested/directory/on/your/server")
# => #<OAuth2::Client:0x00000001204c8288 @id="client_id", @secret="client_sec...
client.auth_code.authorize_url(redirect_uri: "http://localhost:8080/oauth2/callback")
# => "https://example.org/nested/directory/on/your/server/oauth/authorize?client_id=client_id&redirect_uri=http%3A%2F%2Flocalhost%3A8080%2Foauth2%2Fcallback&response_type=code"
```

### Customize `authorize_url` and `token_url`

You can specify custom URLs for authorization and access token, and when using a leading `/` they will _not be relative_, as shown below:

```ruby
client = OAuth2::Client.new(
  "client_id",
  "client_secret",
  site: "https://example.org/nested/directory/on/your/server",
  authorize_url: "/jaunty/authorize/",
  token_url: "/stirrups/access_token",
)
# => #<OAuth2::Client:0x00000001204c8288 @id="client_id", @secret="client_sec...
client.auth_code.authorize_url(redirect_uri: "http://localhost:8080/oauth2/callback")
# => "https://example.org/jaunty/authorize/?client_id=client_id&redirect_uri=http%3A%2F%2Flocalhost%3A8080%2Foauth2%2Fcallback&response_type=code"
client.class.name
# => OAuth2::Client
```

### snake_case and indifferent access in Response#parsed

```ruby
response = access.get("/api/resource", params: {"query_foo" => "bar"})
# Even if the actual response is CamelCase. it will be made available as snaky:
JSON.parse(response.body)         # => {"accessToken"=>"aaaaaaaa", "additionalData"=>"additional"}
response.parsed                   # => {"access_token"=>"aaaaaaaa", "additional_data"=>"additional"}
response.parsed.access_token      # => "aaaaaaaa"
response.parsed[:access_token]    # => "aaaaaaaa"
response.parsed.additional_data   # => "additional"
response.parsed[:additional_data] # => "additional"
response.parsed.class.name        # => OAuth2::SnakyHash (subclass of Hashie::Mash::Rash, from `rash_alt` gem)
```

#### What if I hate snakes and/or indifference?

```ruby
response = access.get("/api/resource", params: {"query_foo" => "bar"}, snaky: false)
JSON.parse(response.body)         # => {"accessToken"=>"aaaaaaaa", "additionalData"=>"additional"}
response.parsed                   # => {"accessToken"=>"aaaaaaaa", "additionalData"=>"additional"}
response.parsed["accessToken"]    # => "aaaaaaaa"
response.parsed["additionalData"] # => "additional"
response.parsed.class.name        # => Hash (just, regular old Hash)
```

<details>
  <summary>Debugging</summary>

Set an environment variable, however you would [normally do that](https://github.com/bkeepers/dotenv).

```ruby
# will log both request and response, including bodies
ENV["OAUTH_DEBUG"] = "true"
```

By default, debug output will go to `$stdout`. This can be overridden when
initializing your OAuth2::Client.

```ruby
require "oauth2"
client = OAuth2::Client.new(
  "client_id",
  "client_secret",
  site: "https://example.org",
  logger: Logger.new("example.log", "weekly"),
)
```
</details>

## OAuth2::Response

The `AccessToken` methods `#get`, `#post`, `#put` and `#delete` and the generic `#request`
will return an instance of the #OAuth2::Response class.

This instance contains a `#parsed` method that will parse the response body and
return a Hash-like [`OAuth2::SnakyHash`](https://gitlab.com/oauth-xx/oauth2/-/blob/main/lib/oauth2/snaky_hash.rb) if the `Content-Type` is `application/x-www-form-urlencoded` or if
the body is a JSON object.  It will return an Array if the body is a JSON
array.  Otherwise, it will return the original body string.

The original response body, headers, and status can be accessed via their
respective methods.

## OAuth2::AccessToken

If you have an existing Access Token for a user, you can initialize an instance
using various class methods including the standard new, `from_hash` (if you have
a hash of the values), or `from_kvform` (if you have an
`application/x-www-form-urlencoded` encoded string of the values).

## OAuth2::Error

On 400+ status code responses, an `OAuth2::Error` will be raised.  If it is a
standard OAuth2 error response, the body will be parsed and `#code` and `#description` will contain the values provided from the error and
`error_description` parameters.  The `#response` property of `OAuth2::Error` will
always contain the `OAuth2::Response` instance.

If you do not want an error to be raised, you may use `:raise_errors => false`
option on initialization of the client.  In this case the `OAuth2::Response`
instance will be returned as usual and on 400+ status code responses, the
Response instance will contain the `OAuth2::Error` instance.

## Authorization Grants

Currently the Authorization Code, Implicit, Resource Owner Password Credentials, Client Credentials, and Assertion
authentication grant types have helper strategy classes that simplify client
use. They are available via the [`#auth_code`](https://gitlab.com/oauth-xx/oauth2/-/blob/main/lib/oauth2/strategy/auth_code.rb),
[`#implicit`](https://gitlab.com/oauth-xx/oauth2/-/blob/main/lib/oauth2/strategy/implicit.rb),
[`#password`](https://gitlab.com/oauth-xx/oauth2/-/blob/main/lib/oauth2/strategy/password.rb),
[`#client_credentials`](https://gitlab.com/oauth-xx/oauth2/-/blob/main/lib/oauth2/strategy/client_credentials.rb), and
[`#assertion`](https://gitlab.com/oauth-xx/oauth2/-/blob/main/lib/oauth2/strategy/assertion.rb) methods respectively.

These aren't full examples, but demonstrative of the differences between usage for each strategy.
```ruby
auth_url = client.auth_code.authorize_url(redirect_uri: "http://localhost:8080/oauth/callback")
access = client.auth_code.get_token("code_value", redirect_uri: "http://localhost:8080/oauth/callback")

auth_url = client.implicit.authorize_url(redirect_uri: "http://localhost:8080/oauth/callback")
# get the token params in the callback and
access = OAuth2::AccessToken.from_kvform(client, query_string)

access = client.password.get_token("username", "password")

access = client.client_credentials.get_token

# Client Assertion Strategy
# see: https://tools.ietf.org/html/rfc7523
claimset = {
  iss: "http://localhost:3001",
  aud: "http://localhost:8080/oauth2/token",
  sub: "me@example.com",
  exp: Time.now.utc.to_i + 3600,
}
assertion_params = [claimset, "HS256", "secret_key"]
access = client.assertion.get_token(assertion_params)

# The `access` (i.e. access token) is then used like so:
access.token # actual access_token string, if you need it somewhere
access.get("/api/stuff") # making api calls with access token
```

If you want to specify additional headers to be sent out with the
request, add a 'headers' hash under 'params':

```ruby
access = client.auth_code.get_token("code_value", redirect_uri: "http://localhost:8080/oauth/callback", headers: {"Some" => "Header"})
```

You can always use the `#request` method on the `OAuth2::Client` instance to make
requests for tokens for any Authentication grant type.

### 🚀 Release Instructions

See [CONTRIBUTING.md][🤝contributing].

## 🔐 Security

See [SECURITY.md][🔐security].

## 🤝 Contributing

If you need some ideas of where to help, you could work on adding more code coverage,
or if it is already 💯 (see [below](#code-coverage)) check TODOs (see [below](#todos)),
or check [issues][🤝issues], or [PRs][🤝pulls],
or use the gem and think about how it could be better.

We [![Keep A Changelog][📗keep-changelog-img]][📗keep-changelog] so if you make changes, remember to update it.

See [CONTRIBUTING.md][🤝contributing] for more detailed instructions.

### Code Coverage

[![Coverage Graph][🔑codecov-g♻️]][🔑codecov]

### 🪇 Code of Conduct

Everyone interacting in this project's codebases, issue trackers,
chat rooms and mailing lists is expected to follow the [![Contributor Covenant 2.1][🪇conduct-img]][🪇conduct].

## 🌈 Contributors

[![Contributors][🖐contributors-img]][🖐contributors]

Made with [contributors-img][🖐contrib-rocks].

Also see GitLab Contributors: [https://gitlab.com/oauth-xx/oauth2/-/graphs/main][🚎contributors-gl]

## ⭐️ Star History

<a href="https://star-history.com/#oauth-xx/oauth2&Date">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=oauth-xx/oauth2&type=Date&theme=dark" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=oauth-xx/oauth2&type=Date" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=oauth-xx/oauth2&type=Date" />
 </picture>
</a>

## 📌 Versioning

This Library adheres to [![Semantic Versioning 2.0.0][📌semver-img]][📌semver].
Violations of this scheme should be reported as bugs.
Specifically, if a minor or patch version is released that breaks backward compatibility,
a new version should be immediately released that restores compatibility.
Breaking changes to the public API will only be introduced with new major versions.

### 📌 Is "Platform Support" part of the public API?

Yes.  But I'm obligated to include notes...

SemVer should, but doesn't explicitly, say that dropping support for specific Platforms
is a *breaking change* to an API.
It is obvious to many, but not all, and since the spec is silent, the bike shedding is endless.

> dropping support for a platform is both obviously and objectively a breaking change

- Jordan Harband (@ljharb, maintainer of SemVer) [in SemVer issue 716][📌semver-breaking]

To get a better understanding of how SemVer is intended to work over a project's lifetime,
read this article from the creator of SemVer:

- ["Major Version Numbers are Not Sacred"][📌major-versions-not-sacred]

As a result of this policy, and the interpretive lens used by the maintainer,
you can (and should) specify a dependency on these libraries using
the [Pessimistic Version Constraint][📌pvc] with two digits of precision.

For example:

```ruby
spec.add_dependency("oauth2", "~> 1.0")
```

See [CHANGELOG.md][📌changelog] for list of releases.

## 📄 License

The gem is available as open source under the terms of
the [MIT License][📄license] [![License: MIT][📄license-img]][📄license-ref].
See [LICENSE.txt][📄license] for the official [Copyright Notice][📄copyright-notice-explainer].


[![FOSSA Status][fossa2-img])][fossa2]

[fossa2]: https://app.fossa.io/projects/git%2Bgithub.com%2Foauth-xx%2Foauth2?ref=badge_large
[fossa2-img]: https://app.fossa.io/api/projects/git%2Bgithub.com%2Foauth-xx%2Foauth2.svg?type=large

### © Copyright

<ul>
    <li>
        2017 - 2025 Peter H. Boling, of
        <a href="https://railsbling.com">
            RailsBling.com
            <picture>
                <img alt="Rails Bling" height="20" src="https://railsbling.com/images/logos/RailsBling-TrainLogo.svg" />
            </picture>
        </a>, and oauth2 contributors
    </li>
    <li>
        Copyright (c) 2011 - 2013 Michael Bleigh and Intridea, Inc.
    </li>
</ul>

## 🤑 One more thing

You made it to the bottom of the page,
so perhaps you'll indulge me for another 20 seconds.
I maintain many dozens of gems, including this one,
because I want Ruby to be a great place for people to solve problems, big and small.
Please consider supporting my efforts via the giant yellow link below,
or one of the others at the head of this README.

[![Buy me a latte][🖇buyme-img]][🖇buyme]

[⛳gg-discussions]: https://groups.google.com/g/oauth-ruby
[⛳gg-discussions-img]: https://img.shields.io/badge/google-group-purple.svg?style=flat

[✇bundle-group-pattern]: https://gist.github.com/pboling/4564780
[⛳️gem-namespace]: https://github.com/oauth-xx/oauth2
[⛳️namespace-img]: https://img.shields.io/badge/namespace-OAuth2-brightgreen.svg?style=flat&logo=ruby&logoColor=white
[⛳️gem-name]: https://rubygems.org/gems/oauth2
[⛳️name-img]: https://img.shields.io/badge/name-oauth2-brightgreen.svg?style=flat&logo=rubygems&logoColor=red
[🚂bdfl-blog]: http://www.railsbling.com/tags/oauth2
[🚂bdfl-blog-img]: https://img.shields.io/badge/blog-railsbling-0093D0.svg?style=for-the-badge&logo=rubyonrails&logoColor=orange
[🚂bdfl-contact]: http://www.railsbling.com/contact
[🚂bdfl-contact-img]: https://img.shields.io/badge/Contact-BDFL-0093D0.svg?style=flat&logo=rubyonrails&logoColor=red
[💖🖇linkedin]: http://www.linkedin.com/in/peterboling
[💖🖇linkedin-img]: https://img.shields.io/badge/PeterBoling-LinkedIn-0B66C2?style=flat&logo=newjapanprowrestling
[💖✌️wellfound]: https://angel.co/u/peter-boling
[💖✌️wellfound-img]: https://img.shields.io/badge/peter--boling-orange?style=flat&logo=wellfound
[💖💲crunchbase]: https://www.crunchbase.com/person/peter-boling
[💖💲crunchbase-img]: https://img.shields.io/badge/peter--boling-purple?style=flat&logo=crunchbase
[💖🐘ruby-mast]: https://ruby.social/@galtzo
[💖🐘ruby-mast-img]: https://img.shields.io/mastodon/follow/109447111526622197?domain=https%3A%2F%2Fruby.social&style=flat&logo=mastodon&label=Ruby%20%40galtzo
[💖🦋bluesky]: https://bsky.app/profile/galtzo.com
[💖🦋bluesky-img]: https://img.shields.io/badge/@galtzo.com-0285FF?style=flat&logo=bluesky&logoColor=white
[💖🌳linktree]: https://linktr.ee/galtzo
[💖🌳linktree-img]: https://img.shields.io/badge/galtzo-purple?style=flat&logo=linktree
[💖💁🏼‍♂️devto]: https://dev.to/galtzo
[💖💁🏼‍♂️devto-img]: https://img.shields.io/badge/dev.to-0A0A0A?style=flat&logo=devdotto&logoColor=white
[💖💁🏼‍♂️aboutme]: https://about.me/peter.boling
[💖💁🏼‍♂️aboutme-img]: https://img.shields.io/badge/about.me-0A0A0A?style=flat&logo=aboutme&logoColor=white
[💖🧊berg]: https://codeberg.org/pboling
[💖🐙hub]: https://github.org/pboling
[💖🛖hut]: https://sr.ht/~galtzo/
[💖🧪lab]: https://gitlab.com/pboling
[👨🏼‍🏫expsup-upwork]: https://www.upwork.com/freelancers/~014942e9b056abdf86?mp_source=share
[👨🏼‍🏫expsup-upwork-img]: https://img.shields.io/badge/UpWork-13544E?style=for-the-badge&logo=Upwork&logoColor=white
[👨🏼‍🏫expsup-codementor]: https://www.codementor.io/peterboling?utm_source=github&utm_medium=button&utm_term=peterboling&utm_campaign=github
[👨🏼‍🏫expsup-codementor-img]: https://img.shields.io/badge/CodeMentor-Get_Help-1abc9c?style=for-the-badge&logo=CodeMentor&logoColor=white
[🏙️entsup-tidelift]: https://tidelift.com/subscription
[🏙️entsup-tidelift-img]: https://img.shields.io/badge/Tidelift_and_Sonar-Enterprise_Support-FD3456?style=for-the-badge&logo=sonar&logoColor=white
[🏙️entsup-tidelift-sonar]: https://blog.tidelift.com/tidelift-joins-sonar
[💁🏼‍♂️peterboling]: http://www.peterboling.com
[🚂railsbling]: http://www.railsbling.com
[📜src-gl-img]: https://img.shields.io/badge/GitLab-FBA326?style=for-the-badge&logo=Gitlab&logoColor=orange
[📜src-gl]: https://gitlab.com/oauth-xx/oauth2/
[📜src-cb-img]: https://img.shields.io/badge/CodeBerg-4893CC?style=for-the-badge&logo=CodeBerg&logoColor=blue
[📜src-cb]: https://codeberg.org/oauth-xx/oauth2
[📜src-gh-img]: https://img.shields.io/badge/GitHub-238636?style=for-the-badge&logo=Github&logoColor=green
[📜src-gh]: https://github.com/oauth-xx/oauth2
[📜docs-cr-rd-img]: https://img.shields.io/badge/RubyDoc-Current_Release-943CD2?style=for-the-badge&logo=readthedocs&logoColor=white
[📜docs-head-rd-img]: https://img.shields.io/badge/RubyDoc-HEAD-943CD2?style=for-the-badge&logo=readthedocs&logoColor=white
[📜wiki]: https://gitlab.com/oauth-xx/oauth2/-/wikis/home
[📜wiki-img]: https://img.shields.io/badge/wiki-examples-943CD2.svg?style=for-the-badge&logo=Wiki&logoColor=white
[👽dl-rank]: https://rubygems.org/gems/oauth2
[👽dl-ranki]: https://img.shields.io/gem/rd/oauth2.svg
[👽oss-help]: https://www.codetriage.com/oauth-xx/oauth2
[👽oss-helpi]: https://www.codetriage.com/oauth-xx/oauth2/badges/users.svg
[👽version]: https://rubygems.org/gems/oauth2
[👽versioni]: https://img.shields.io/gem/v/oauth2.svg
[🔑cc-mnt]: https://qlty.sh/gh/oauth-xx/projects/oauth2
[🔑cc-mnti♻️]: https://qlty.sh/badges/d3370c2c-8791-4202-9759-76f527f76005/maintainability.svg
[🔑cc-cov]: https://qlty.sh/gh/oauth-xx/projects/oauth2
[🔑cc-covi♻️]: https://qlty.sh/badges/d3370c2c-8791-4202-9759-76f527f76005/test_coverage.svg
[🔑codecov]: https://codecov.io/gh/oauth-xx/oauth2
[🔑codecovi♻️]: https://codecov.io/gh/oauth-xx/oauth2/branch/main/graph/badge.svg?token=bNqSzNiuo2
[🔑coveralls]: https://coveralls.io/github/oauth-xx/oauth2?branch=main
[🔑coveralls-img]: https://coveralls.io/repos/github/oauth-xx/oauth2/badge.svg?branch=main
[🔑depfu]: https://depfu.com/github/oauth-xx/oauth2?project_id=5884
[🔑depfui♻️]: https://badges.depfu.com/badges/6d34dc1ba682bbdf9ae2a97848241743/count.svg
[🖐codeQL]: https://github.com/oauth-xx/oauth2/security/code-scanning
[🖐codeQL-img]: https://github.com/oauth-xx/oauth2/actions/workflows/codeql-analysis.yml/badge.svg
[🚎1-an-wf]: https://github.com/oauth-xx/oauth2/actions/workflows/ancient.yml
[🚎1-an-wfi]: https://github.com/oauth-xx/oauth2/actions/workflows/ancient.yml/badge.svg
[🚎2-cov-wf]: https://github.com/oauth-xx/oauth2/actions/workflows/coverage.yml
[🚎2-cov-wfi]: https://github.com/oauth-xx/oauth2/actions/workflows/coverage.yml/badge.svg
[🚎3-hd-wf]: https://github.com/oauth-xx/oauth2/actions/workflows/heads.yml
[🚎3-hd-wfi]: https://github.com/oauth-xx/oauth2/actions/workflows/heads.yml/badge.svg
[🚎4-lg-wf]: https://github.com/oauth-xx/oauth2/actions/workflows/legacy.yml
[🚎4-lg-wfi]: https://github.com/oauth-xx/oauth2/actions/workflows/legacy.yml/badge.svg
[🚎5-st-wf]: https://github.com/oauth-xx/oauth2/actions/workflows/style.yml
[🚎5-st-wfi]: https://github.com/oauth-xx/oauth2/actions/workflows/style.yml/badge.svg
[🚎6-s-wf]: https://github.com/oauth-xx/oauth2/actions/workflows/supported.yml
[🚎6-s-wfi]: https://github.com/oauth-xx/oauth2/actions/workflows/supported.yml/badge.svg
[🚎7-us-wf]: https://github.com/oauth-xx/oauth2/actions/workflows/unsupported.yml
[🚎7-us-wfi]: https://github.com/oauth-xx/oauth2/actions/workflows/unsupported.yml/badge.svg
[🚎8-ho-wf]: https://github.com/oauth-xx/oauth2/actions/workflows/hoary.yml
[🚎8-ho-wfi]: https://github.com/oauth-xx/oauth2/actions/workflows/hoary.yml/badge.svg
[🚎9-t-wf]: https://github.com/oauth-xx/oauth2/actions/workflows/truffle.yml
[🚎9-t-wfi]: https://github.com/oauth-xx/oauth2/actions/workflows/truffle.yml/badge.svg
[🚎10-j-wf]: https://github.com/oauth-xx/oauth2/actions/workflows/jruby.yml
[🚎10-j-wfi]: https://github.com/oauth-xx/oauth2/actions/workflows/jruby.yml/badge.svg
[🚎11-c-wf]: https://github.com/oauth-xx/oauth2/actions/workflows/current.yml
[🚎11-c-wfi]: https://github.com/oauth-xx/oauth2/actions/workflows/current.yml/badge.svg
[⛳liberapay-img]: https://img.shields.io/liberapay/goal/pboling.svg?logo=liberapay
[⛳liberapay]: https://liberapay.com/pboling/donate
[🖇sponsor-img]: https://img.shields.io/badge/Sponsor_Me!-pboling.svg?style=social&logo=github
[🖇sponsor]: https://github.com/sponsors/pboling
[🖇polar-img]: https://img.shields.io/badge/polar-donate-yellow.svg
[🖇polar]: https://polar.sh/pboling
[🖇kofi-img]: https://img.shields.io/badge/a_more_different_coffee-✓-yellow.svg
[🖇kofi]: https://ko-fi.com/O5O86SNP4
[🖇patreon-img]: https://img.shields.io/badge/patreon-donate-yellow.svg
[🖇patreon]: https://patreon.com/galtzo
[🖇buyme-img]: https://img.buymeacoffee.com/button-api/?text=Buy%20me%20a%20latte&emoji=&slug=pboling&button_colour=FFDD00&font_colour=000000&font_family=Cookie&outline_colour=000000&coffee_colour=ffffff
[🖇buyme]: https://www.buymeacoffee.com/pboling
[🖇buyme-small-img]: https://img.shields.io/badge/buy_me_a_coffee-✓-yellow.svg?style=flat
[💎ruby-2.3i]: https://img.shields.io/badge/Ruby-2.3-DF00CA?style=for-the-badge&logo=ruby&logoColor=white
[💎ruby-2.4i]: https://img.shields.io/badge/Ruby-2.4-DF00CA?style=for-the-badge&logo=ruby&logoColor=white
[💎ruby-2.5i]: https://img.shields.io/badge/Ruby-2.5-DF00CA?style=for-the-badge&logo=ruby&logoColor=white
[💎ruby-2.6i]: https://img.shields.io/badge/Ruby-2.6-DF00CA?style=for-the-badge&logo=ruby&logoColor=white
[💎ruby-2.7i]: https://img.shields.io/badge/Ruby-2.7-DF00CA?style=for-the-badge&logo=ruby&logoColor=white
[💎ruby-3.0i]: https://img.shields.io/badge/Ruby-3.0-CC342D?style=for-the-badge&logo=ruby&logoColor=white
[💎ruby-3.1i]: https://img.shields.io/badge/Ruby-3.1-CC342D?style=for-the-badge&logo=ruby&logoColor=white
[💎ruby-3.2i]: https://img.shields.io/badge/Ruby-3.2-CC342D?style=for-the-badge&logo=ruby&logoColor=white
[💎ruby-3.3i]: https://img.shields.io/badge/Ruby-3.3-CC342D?style=for-the-badge&logo=ruby&logoColor=white
[💎ruby-c-i]: https://img.shields.io/badge/Ruby-current-CC342D?style=for-the-badge&logo=ruby&logoColor=green
[💎ruby-headi]: https://img.shields.io/badge/Ruby-HEAD-CC342D?style=for-the-badge&logo=ruby&logoColor=blue
[💎truby-22.3i]: https://img.shields.io/badge/Truffle_Ruby-22.3-34BCB1?style=for-the-badge&logo=ruby&logoColor=pink
[💎truby-23.0i]: https://img.shields.io/badge/Truffle_Ruby-23.0-34BCB1?style=for-the-badge&logo=ruby&logoColor=pink
[💎truby-23.1i]: https://img.shields.io/badge/Truffle_Ruby-23.1-34BCB1?style=for-the-badge&logo=ruby&logoColor=pink
[💎truby-c-i]: https://img.shields.io/badge/Truffle_Ruby-current-34BCB1?style=for-the-badge&logo=ruby&logoColor=green
[💎truby-headi]: https://img.shields.io/badge/Truffle_Ruby-HEAD-34BCB1?style=for-the-badge&logo=ruby&logoColor=blue
[💎jruby-9.1i]: https://img.shields.io/badge/JRuby-9.1-FBE742?style=for-the-badge&logo=ruby&logoColor=red
[💎jruby-9.2i]: https://img.shields.io/badge/JRuby-9.2-FBE742?style=for-the-badge&logo=ruby&logoColor=red
[💎jruby-9.3i]: https://img.shields.io/badge/JRuby-9.3-FBE742?style=for-the-badge&logo=ruby&logoColor=red
[💎jruby-9.4i]: https://img.shields.io/badge/JRuby-9.4-FBE742?style=for-the-badge&logo=ruby&logoColor=red
[💎jruby-c-i]: https://img.shields.io/badge/JRuby-current-FBE742?style=for-the-badge&logo=ruby&logoColor=green
[💎jruby-headi]: https://img.shields.io/badge/JRuby-HEAD-FBE742?style=for-the-badge&logo=ruby&logoColor=blue
[🤝issues]: https://github.com/oauth-xx/oauth2/issues
[🤝pulls]: https://github.com/oauth-xx/oauth2/pulls
[🤝contributing]: CONTRIBUTING.md
[🔑codecov-g♻️]: https://codecov.io/gh/oauth-xx/oauth2/graphs/tree.svg?token=bNqSzNiuo2
[🖐contrib-rocks]: https://contrib.rocks
[🖐contributors]: https://github.com/oauth-xx/oauth2/graphs/contributors
[🖐contributors-img]: https://contrib.rocks/image?repo=oauth-xx/oauth2
[🚎contributors-gl]: https://gitlab.com/oauth-xx/oauth2/-/graphs/main
[🪇conduct]: CODE_OF_CONDUCT.md
[🪇conduct-img]: https://img.shields.io/badge/Contributor_Covenant-2.1-4baaaa.svg
[📌pvc]: http://guides.rubygems.org/patterns/#pessimistic-version-constraint
[📌semver]: https://semver.org/spec/v2.0.0.html
[📌semver-img]: https://img.shields.io/badge/semver-2.0.0-FFDD67.svg?style=flat
[📌semver-breaking]: https://github.com/semver/semver/issues/716#issuecomment-869336139
[📌major-versions-not-sacred]: https://tom.preston-werner.com/2022/05/23/major-version-numbers-are-not-sacred.html
[📌changelog]: CHANGELOG.md
[📗keep-changelog]: https://keepachangelog.com/en/1.0.0/
[📗keep-changelog-img]: https://img.shields.io/badge/keep--a--changelog-1.0.0-FFDD67.svg?style=flat
[📌gitmoji]:https://gitmoji.dev
[📌gitmoji-img]:https://img.shields.io/badge/gitmoji-%20😜%20😍-FFDD67.svg?style=flat-square
[🧮kloc]: https://www.youtube.com/watch?v=dQw4w9WgXcQ
[🧮kloc-img]: https://img.shields.io/badge/KLOC-0.073-FFDD67.svg?style=for-the-badge&logo=YouTube&logoColor=blue
[🔐security]: SECURITY.md
[🔐security-img]: https://img.shields.io/badge/security-policy-brightgreen.svg?style=flat
[📄copyright-notice-explainer]: https://opensource.stackexchange.com/questions/5778/why-do-licenses-such-as-the-mit-license-specify-a-single-year
[📄license]: LICENSE.txt
[📄license-ref]: https://opensource.org/licenses/MIT
[📄license-img]: https://img.shields.io/badge/License-MIT-green.svg
[📄ilo-declaration]: https://www.ilo.org/declaration/lang--en/index.htm
[📄ilo-declaration-img]: https://img.shields.io/badge/ILO_Fundamental_Principles-✓-brightgreen.svg?style=flat
[🚎yard-current]: http://rubydoc.info/gems/oauth2
[🚎yard-head]: https://rubydoc.info/github/oauth-xx/oauth2/main
[💎stone_checksums]: https://github.com/pboling/stone_checksums
[💎SHA_checksums]: https://gitlab.com/oauth-xx/oauth2/-/tree/main/checksums
[💎rlts]: https://github.com/rubocop-lts/rubocop-lts
[💎rlts-img]: https://img.shields.io/badge/code_style-rubocop--lts-brightgreen.svg?plastic&logo=ruby&logoColor=white
[🏘fossa]: https://app.fossa.io/projects/git%2Bgithub.com%2Foauth-xx%2Foauth2?ref=badge_shield
[🏘fossa-img]: https://app.fossa.io/api/projects/git%2Bgithub.com%2Foauth-xx%2Foauth2.svg?type=shield

<details>
  <summary>
    rel="me" Social Proofs
  </summary>

<a rel="me" alt="Follow me on Ruby.social" href="https://ruby.social/@galtzo"><img src="https://img.shields.io/mastodon/follow/109447111526622197?domain=https%3A%2F%2Fruby.social&style=social&label=Follow%20%40galtzo%20on%20Ruby.social"></a>
<a rel="me" alt="Follow me on FLOSS.social" href="https://floss.social/@galtzo"><img src="https://img.shields.io/mastodon/follow/110304921404405715?domain=https%3A%2F%2Ffloss.social&style=social&label=Follow%20%40galtzo%20on%20Floss.social"></a>
</details>
