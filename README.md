# state_machine_rspec

Custom matchers for [pluginaweek/state_machine](https://github.com/pluginaweek/state_machine).

## Installation

Add this line to your application's Gemfile:

    gem 'state_machine_rspec'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install state_machine_rspec

## Matchers

### `respond_to_events`

```ruby
describe Vehicle do
  let(:vehicle) { Vehicle.new }
  context 'when in third gear' do
    before { vehicle.state = :third_gear.to_s }

    it { should respond_to_events :shift_down, :crash }
    it { should_not respond_to_events :park, :ignite, :idle,
                                      :shift_up, :repair }
  end
end
```


## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
