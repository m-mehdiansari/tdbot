# tdbot 1.6.3
**tdbot source for telegram clinet bots by [@vysheng](https://github.com/vysheng)**

[Telegram Tdlib](https://github.com/tdlib/td) is a complete library for creating telegram clients, it also has a simple tdjson ready-to-use library to ease the integration with different programming languages and platforms.
This plugin is a complete tdlib-tdjson binding package to help you create your own Telegram clients.

# complie tdbot 
<table style="width:100%" dir="lft">
   <tr>
      <th colspan="3">System required for compilation</th>
   </tr>
   <tr>
     <td colspan="2">CPU</td>
     <td align="center">2 Core</td>
    </tr>
    <tr>
     <td colspan="2">RAM</td>
     <td align="center">4GB</td>
    </tr>
    <tr>
     <td colspan="2">HHD</td>
     <td align="center">500 MB</td>
    </tr>
    <tr>
     <td colspan="2">OS</td>
     <td align="center">ubuntu 16.04 x64</td>
    </tr>
</table>

> for use tdbot you need compile tdbot!

> open new terminal:

**for auto make tdbot**
```
* cd && git clone https://github.com/m-mehdiansari/tdbot.git
* chmod +x Sky
* ./Sky
```
Enter api_hash and api_id and then continue.

**for manual make telegram-bot**
> put telegram.h and insert api_hash in line 27 and insert api_id in line 28 
```
* sudo apt-get update && sudo apt-get upgrade -y
* sudo apt install git build-essential cmake libssl-dev liblua5.2-dev gperf libconfig++-dev
* sudo apt-get install make git zlib1g-dev  gperf php cmake g++
* git clone https://github.com/tdlib/td.git
* mkdir build && cd build && cmake ..
* export CXXFLAGS=""
* cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX:PATH=../tdlib -DTD_ENABLE_LTO=ON ..
* cmake --build . --target install
```


Finally, copy and use the telegram-bot file in the tdbot/bulid path.

# tdbot profile config file
To log in to tdbot you need to create a profile
```
# This is an empty config file
# Feel free to put something here

default_profile = "main";

main =  {
  # connect to totally separate telegram environment
  # it is used only for tests
  # false is default value
  test = false;
  
  # folder containing data for this profile
  # default value is profile name
  config_directory = "main";
  
  # language code. Some telegram notifications
  # may use it. Default is "en"
  language_code = "en";

  # use file db. Allows files reuse after restart
  # default value is true
  use_file_db = true;
  
  # use file garbage collector. Deletes files unused for 30 days
  # default value is true
  use_file_gc = true;

  # use file names as specified in document description
  # instead telegram-bot can use random names
  # default value is true
  file_readable_names = true;

  # allow accepting and creating secret chats
  # default value is true
  use_secret_chats = true;

  # use chat info db. Allow to send messages to chats instantly after restart
  # default value is true
  use_chat_info_db = true;

  # use message db
  # default value is true
  use_message_db = true;

  # logname. if not starts with '/' is relative to config_directory
  # if empty log to stderr
  # default value is empty
  logname = "log.txt";

  # log verbosity. Default value is 0
  verbosity = 2;

  # LUA script to use. If empty do not use lua. Relative to config_directory
  # default value is empty
  lua_script = "script.lua";
};

test_dc1 = {
  test = true;
  verbosity = 100;
  logname = "log.txt";
};

# in many cases default values are OK, so config is empty
second = {
};
```
# login tdbot

First of all you need to create config. Default config name is `${HOME}/.telegram-bot/config`. Then you need to login

**If you want to login as bot**
```
./tdbot -c config-file --login --bot=$token
```
**If you want to login as user**
```
./tdbot -c config-file --login --phone=$phone_number
```

# launch tdbot

**if you want launch bot:**
```
./tdbot -c config-file
```
