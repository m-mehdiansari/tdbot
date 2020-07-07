# tdbot 1.6.3
<h3 align="right"><a href="https://github.com/vysheng">@vysheng</a> تلگرام بات نوشته شده توسط </h3>

<p dir="rtl">
<a href="https://github.com/tdlib/td">Telegram Tdlib</a> یک کتابخانه کامل برای ایجاد ربات های تلگرام است ، همچنین دارای یک کتابخانه آماده برای استفاده tdjson برای سهولت در ادغام با زبان ها و سیستم عامل های مختلف برنامه نویسی است.
این افزونه یک بسته کامل اتصال tdlib-tdjson است که به شما کمک می کند تا ربات های Telegram خود را ایجاد کنید.
<br></p>

<h1 align="right">tdbot ساخت</h1>
<table style="width:100%" dir="rtl">
   <tr>
      <th colspan="3">سیستم مورد نیاز</th>
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
<p dir="rtl"> > برای ساخت تیدی بات شما ابتدا باید ان را بسازید!</p>

<h3 align="right">:برای ساخت تلگرام بات</h3>

```
cd $HOME && git clone https://github.com/m-mehdiansari/tdbot.git
```

<p dir="rtl"> > فایل telegram.h را باز کنید و سپس api_hash را در لاین 27 جایگزین کنید و سپس api_id را در لاین 28 جایگزین کنید!</p>

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
<p dir="rtl"> > در آخر، فایل telegram-bot را از مسیر tdbot/bulid کپی و استفاده کنید.</p>

<h2 align="right">ساخت فایل پروفایل ربات</h2>

<p dir="rtl"> > شما برای لاگین بر روی tdbot نیاز به ساخت فایل پروفایل دارید!<br>توجه داشته باشید کامند هایی درون کد نیازی نیست در فایل قرار دهید.</p>

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
<h2 align="right">tdbot لاگین بر روی</h2>

<p dir="rtl"> > در آغاز شما نیاز به ساخت فایل پروفایل دارید. مسیر فایل پروفایل به صورت پیش فرض بر روی مسیر <code align="left">${HOME}/.telegram-bot/config</code> قرار دارد. انگاه میتوانید لاگین کنید.</p>

<h4 align="right">لاگین کنید api اگر میخواهید به عنوان یک ربات</h4>

```
./tdbot -c config-file --login --bot=$token
```

<h4 align="right">اگر میخواهید به عنوان یک کاربر لاگین کنید</h4>

```
./tdbot -c config-file --login --phone=$phone_number
```

<h2 align="right">tdbot اجرای</h2>

<h4 align="right">.اگر میخواهید ربات را راه اندازی کنید</h4>

```
./tdbot -c config-file
```

<h2 align="right">ترجمه ها</h2>

[Engish](https://github.com/m-mehdiansari/tdbot/blob/master/README.md)
