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
* Setting your database name of the the projects.
* Setting up the table. Import 2 .sql files to your database.
a. For Auth Tokens
<pre><code>
DROP TABLE IF EXISTS `auth_tokens`;
CREATE TABLE `auth_tokens`  (
  `id_auth` int(10) UNSIGNED NOT NULL AUTO_INCREMENT,
  `token` char(255) CHARACTER SET latin1 COLLATE latin1_swedish_ci NULL DEFAULT NULL,
  `id_user` varchar(100) CHARACTER SET latin1 COLLATE latin1_swedish_ci NULL DEFAULT NULL,
  `site_url` varchar(255) CHARACTER SET latin1 COLLATE latin1_swedish_ci NULL DEFAULT NULL,
  `ip_address` varchar(255) CHARACTER SET latin1 COLLATE latin1_swedish_ci NULL DEFAULT NULL,
  `expires` int(11) NULL DEFAULT NULL,
  `iat` datetime(0) NULL DEFAULT NULL,
  `uat` timestamp(0) NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP(0),
  PRIMARY KEY (`id_auth`) USING BTREE
) ENGINE = InnoDB AUTO_INCREMENT = 20 CHARACTER SET = latin1 COLLATE = latin1_swedish_ci ROW_FORMAT = Compact;
</code></pre>
b. For Users (Default Username : Admin, Password: bukabuka)
<pre><code>
DROP TABLE IF EXISTS `users`;
CREATE TABLE `users`  (
  `id_user` varchar(100) CHARACTER SET latin1 COLLATE latin1_swedish_ci NOT NULL,
  `fullname` varchar(50) CHARACTER SET latin1 COLLATE latin1_swedish_ci NOT NULL,
  `notelp` varchar(13) CHARACTER SET latin1 COLLATE latin1_swedish_ci NOT NULL,
  `email` varchar(50) CHARACTER SET latin1 COLLATE latin1_swedish_ci NOT NULL,
  `username` varchar(32) CHARACTER SET latin1 COLLATE latin1_swedish_ci NOT NULL,
  `password` varchar(255) CHARACTER SET latin1 COLLATE latin1_swedish_ci NOT NULL,
  `foto` varchar(255) CHARACTER SET latin1 COLLATE latin1_swedish_ci NOT NULL,
  `roles` varchar(255) CHARACTER SET latin1 COLLATE latin1_swedish_ci NOT NULL,
  `iat` datetime(0) NOT NULL,
  `uat` timestamp(0) NOT NULL ON UPDATE CURRENT_TIMESTAMP(0),
  PRIMARY KEY (`id_user`) USING BTREE,
  UNIQUE INDEX `username`(`username`) USING BTREE
) ENGINE = InnoDB CHARACTER SET = latin1 COLLATE = latin1_swedish_ci ROW_FORMAT = Compact;

-- ----------------------------
-- Records of users
-- ----------------------------
INSERT INTO `users` VALUES ('143221231', 'Rahma H Slamet', '081344966375', 'itsme.arhen@gmail.com', 'admin', '$2y$10$Wm88uKSK.7dKcgARHThAh.BPKJrJmmG8QHsqujM5XwByw.9dkaDAi', '', 'admin', '2017-08-03 11:00:00', '2018-11-09 16:02:33');
</code></pre>

## Usage 
uauth support basic authentication and authorization.Below is information about available method in the current version.

| Method | Usage | parameters | Return type
| ------ | ------ | ------ | ------ |
| Login | `$this->uauth->login` | `$username, $password, $remember`(support 1/0, true/false, checked/unchecked) | true / false
| Logout | `$this->uauth->logout` | - | -
| Get Roles | `$this->uauth->getRoles` | - | array / null
| Authorization | `$this->uauth->authorization` | `$string_roles` (if more than 1 roles, separate by  `','` ) type : ``('admin,editor,author')`` | true / fgitalse
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
