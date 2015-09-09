## Installation

Add [RuboCop](https://github.com/bbatsov/rubocop) to `Gemfile`:

```
gem 'rubocop', :require => false
```

Install bundle:

```
$ bundle
```

Put `.rubocop.yml` in the root of your project:

```
$ curl -O https://raw.githubusercontent.com/Gera-IT/gerait_rubocop_config/master/.rubocop.yml
```

Run RuboCop:
```
$ rubocop
```

## Use RuboCop with Jenkins

### Requirements

- [Checkstyle Jenkins plugin](https://wiki.jenkins-ci.org/display/JENKINS/Checkstyle+Plugin)

Add `rubocop` and `rubocop-checkstyle-formatter` gem to Gemfile:

```
gem 'rubocop', :require => false
gem 'rubocop-checkstyle_formatter', :require => false
```

Install bundle:

```
$ bundle
```

Put `.rubocop.yml` in the root of your project:

```
$ curl -O https://raw.githubusercontent.com/Gera-IT/gerait_rubocop_config/master/.rubocop.yml
```

Configure your Jenkins job to perform this command during build:

```
rubocop --require rubocop/formatter/checkstyle_formatter --format RuboCop::Formatter::CheckstyleFormatter --no-color --out tmp/rubocop_checkstyle.xml || true
```
Add post-build action 'Publish Checkstyle analysis results' and configure Checkstyle results to 'tmp/rubocop_checkstyle.xml'.

## Disabled Cops
```
Style/AutoResourceCleanup
Style/ClassAndModuleChildren
Style/Copyright
Style/Documentation
Style/Encoding
Style/HashSyntax
Style/InlineComment
Style/Lambda
Style/MethodCalledOnDoEndBlock
Style/MissingElse
Style/Next
Style/OptionHash
Style/Send
```
