# Uauth
---------------------------------------------------------
Uauth is a simple Authentication library for Codeigniter made by Arhen at Upana Studio.
Using this library, you can

  - Login / Logout
  - Remember Me
  - Username/Passowrd Wrong Errors
  - Session Timeout with returning last url
  - forgot password
  - Authentication login
  - Support Roles
  - 403 forbidden access handling

## Installation

uath require **php7.x** dan **Codeiginiter >=3.x**
##### Using Download 
Download this github, then copy its content to your fresh/existing codeiginiter project.
##### Using terminal direct into your project


```sh
$ cd your-projects
$ git clone https://github.com/upanastudio/uauth.git
$ cp -a uauth/. application/.
```

## Setup

You need to configuration some files before using it properly.
* Open file /application/helpers/my_url_helper.php
* Edit the login url, logout url, admin url as you wish.

## Usage 
uauth support basic authentication and authorization.Below is information about available method in the current version.

| Method | Usage | parameters | Return type
| ------ | ------ | ------ | ------ |
| Login | `$this->uauth->login` | `$username, $password, $remember`(support 1/0, true/false, checked/unchecked) | true / false
| Logout | `$this->uauth->logout` | - | -
| Get Roles | `$this->uauth->getRoles` | - | array / null
| Authorization | `$this->uauth->authorization` | `$string_roles` (if more than 1 roles, separate by  `','` ) type : ``('admin,editor,author')`` | true / false
| Get UserId | `$this->uauth->getUserId` | - | `userId string` / null
| IsLogin | `$this->uauth->isLogin` | - | true / false


## Development

Want to contribute? Great!

We want to make this auth powerfull but keep it simple as possible. Just open your favorite editor and start code right now. Then make a PR if you have some idea about stuff.

### Coming Soon Feature
* Management Roles

License
----

MIT


**Free Software, Hell Yeah!**

[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)
