# TurboPower Rails

`turbo_power` is a power-pack for Turbo Streams. This gem provides server-side Ruby helpers for the NPM package [`turbo_power`](https://github.com/marcoroth/turbo_power).

## Important Note

This is very much a work in progress right now. There are some open Pull Requests against [`turbo-rails`](https://github.com/hotwired/turbo-rails) which are needed for this to work properly:

* https://github.com/hotwired/turbo-rails/pull/373
* https://github.com/hotwired/turbo-rails/pull/374
* https://github.com/hotwired/turbo-rails/pull/375

This also requires `@hotwired/rails >= 7.2.0-beta.2`.

**Also:** I can't guarantee that the current API stays that way, there might be even more ways to improve it.

### Workaround for the open Pull Requests

Then only workaround to play with this gem right now is to point the gem against GitHub repos:

```ruby
# Gemfile

gem "turbo-rails", github: "marcoroth/turbo-rails", branch: "custom-action-helpers"
gem "turbo_power", github: "marcoroth/turbo_pack-rails", branch: "main"
gem "turbo_ready", github: "marcoroth/turbo_ready", branch: "main"
```

## Installation

Install the gem and add to the application's Gemfile by executing:

```shell
bundle add turbo_power
```

Install the JavaScript package:

```shell
yarn add turbo_power @hotwired/turbo@next
```

Initialize TurboPower in `application.js`:

```diff
// application.js
import * as Turbo from '@hotwired/turbo'

+import TurboPower from 'turbo_power'
+TurboPower.initialize(Turbo.StreamActions)
```

## Usage

### Actions from `turbo_ready`

* [`turbo_stream.invoke(method, *args, selector: nil, camelize: true, id: nil)`](https://github.com/hopsoft/turbo_ready)

### Actions from `turbo-morph`

* [`turbo_stream.morph(target, html = nil, **attributes, &block)`](https://github.com/marcoroth/turbo-morph)

### DOM Actions

* `turbo_stream.graft(target, parent, **attributes)`
* `turbo_stream.inner_html(target, html = nil, **attributes, &block)`
* `turbo_stream.insert_adjacent_html(target, html = nil, position: 'beforeend', **attributes, &block)`
* `turbo_stream.insert_adjacent_text(target, text, position: 'beforebegin', **attributes)`
* `turbo_stream.morph(target, html = nil, **attribtues, &block)`
* `turbo_stream.outer_html(target, html = nil, **attributes, &block)`
* `turbo_stream.text_content(target, text, **attributes)`
* `turbo_stream.set_meta(name, content, **attributes)`


### Attribute Actions

* `turbo_stream.add_css_class(target, classes, **attributes)`
* `turbo_stream.remove_attribute(target, attribute, **attributes)`
* `turbo_stream.remove_css_class(target, classes, **attributes)`
* `turbo_stream.set_attribute(target, attribute, value, **attributes)`
* `turbo_stream.set_dataset_attribute(target, attribute, value, **attributes)`
* `turbo_stream.set_property(target, property, value, **attributes)`
* `turbo_stream.set_style(target, name, value, **attributes)`
* `turbo_stream.set_styles(target, styles, **attributes)`
* `turbo_stream.set_value(target, value, **attributes)`


### Event Actions

* `turbo_stream.dispatch_event(target, name, detail: {}, **attributes)`


### Storage Actions

* `turbo_stream.clear_storage(type, **attributes)`
* `turbo_stream.clear_local_storage(**attributes)`
* `turbo_stream.clear_session_storage(**attributes)`
* `turbo_stream.remove_storage_item(key, type, **attributes)`
* `turbo_stream.remove_local_storage_item(key, **attributes)`
* `turbo_stream.remove_session_storage_item(key, **attributes)`
* `turbo_stream.set_storage_item(key, value, type, **attributes)`
* `turbo_stream.set_local_storage_item(key, value, **attributes)`
* `turbo_stream.set_session_storage_item(key, value, **attributes)`


### Browser Actions

* `turbo_stream.redirect_to(url, action_name = nil, **attributes)`
* `turbo_stream.reload(**attributes)`
* `turbo_stream.scroll_into_view(target, inline = "nearest", **attributes)`
* `turbo_stream.set_cookie(cookie, **attributes)`
* `turbo_stream.set_cookie_item(key, value, **attributes)`
* `turbo_stream.set_focus(target, **attributes)`


### Browser History Actions

* `turbo_stream.history_go(delta, **attributes)`
* `turbo_stream.push_state(url, title = nil, state = nil, **attributes)`
* `turbo_stream.replace_state(url, title = nil, state = nil, **attributes)`


### Debug Actions

* `turbo_stream.console_log(message, level = 'log', **attributes)`
* `turbo_stream.console_table(data, columns, **attributes)`

### Notification Actions

* `turbo_stream.notification(title, options, **attributes)`

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake test` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and the created tag, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/marcoroth/turbo_power-rails. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [code of conduct](https://github.com/marcoroth/turbo_power-rails/blob/master/CODE_OF_CONDUCT.md).

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## Code of Conduct

Everyone interacting in the TurboPower project's codebases, issue trackers, chat rooms and mailing lists is expected to follow the [code of conduct](https://github.com/marcoroth/turbo_power-rails/blob/master/CODE_OF_CONDUCT.md).
