teamspeak-ruby
----------
Ruby interface for TeamSpeak 3's [server query](http://media.teamspeak.com/ts3_literature/
TeamSpeak%203%20Server%20Query%20Manual.pdf) api.

Install
----------
```shell
gem install teamspeak-ruby
```

Usage
----------
```ruby
require 'teamspeak-ruby'

ts = Teamspeak.new('127.0.0.1')
ts.login('serveradmin', 'T5I3A1G8')
ts.command('use', {'sid' => 1})

ts.command('clientlist').each do |user|
  if user['client_nickname'] == 'Example Client'
    ts.command('clientpoke', {'clid' => user['clid'], 'msg' => 'Just an example!'})
  end
end

ts.disconnect
```

TODO
----------
- Proper error handling.
- Automatic testing