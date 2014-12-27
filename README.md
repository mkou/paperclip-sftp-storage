Paperclip sftp Storage
======================

Allow [Paperclip](https://github.com/thoughtbot/paperclip) attachments to be stored on SFTP servers. Inspired from [paperclip-storage-ftp] (https://github.com/xing/paperclip-storage-ftp)



## Usage

Somewhere in your code:

```ruby
require "paperclip/storage/sftp"
```

In your model:

```ruby
class User < ActiveRecord::Base
  has_attached_file :avatar,

    # Choose the SFTP storage backend
    :storage => :sftp,
    # The list of SFTP options
    :sftp_options => [
      {
        :host      => "sftp.example.com",
        :directory => "my_assets_repository", #optional
        :path      => ":attachment/:id/:style/:filename",
        :user      => "foo"
      }
end
```
