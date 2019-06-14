# sample-web-server
テクノロジー（藤原）Node.jsによるサンプルWebサーバ

```
全部貼っちゃいました。すみません
 cd fujiwara

~/fujiwara master*
❯ git clone git@github.com:aaabfly/sample-web-server.git
Cloning into 'sample-web-server'...
remote: Enumerating objects: 7, done.
remote: Counting objects: 100% (7/7), done.
remote: Compressing objects: 100% (5/5), done.
remote: Total 7 (delta 1), reused 5 (delta 1), pack-reused 0
Receiving objects: 100% (7/7), done.
Resolving deltas: 100% (1/1), done.

~/fujiwara master*
❯ ls
README.md             learning-http-message simple-web-site
hello-git             sample-web-server

~/fujiwara master*
❯ cd sample-web-server

~/fujiwara/sample-web-server master
❯ code .

~/fujiwara/sample-web-server master
❯ curl --silent --request GET --url https://api.thecatapi.com/v1/images/searchvv

~/fujiwara/sample-web-server master
❯ curl --silent --request GET --url https://api.thecatapi.com/v1/images/search
[{"breeds":[],"id":"H73xMj6Sg","url":"https://cdn2.thecatapi.com/images/H73xMj6Sg.jpg","width":960,"height":1280}]
~/fujiwara/sample-web-server master
❯ curl --silent --request GET --url 'https://api.thecatapi.com/v1/images/search?limit=3'
[{"breeds":[],"id":"7sk","url":"https://cdn2.thecatapi.com/images/7sk.gif","width":256,"height":192},{"breeds":[],"id":"e4g","url":"https://cdn2.thecatapi.com/images/e4g.gif","width":400,"height":605},{"breeds":[{"weight":{"imperial":"8 - 16","metric":"4 - 7"},"id":"sibe","name":"Siberian","cfa_url":"http://cfa.org/Breeds/BreedsSthruT/Siberian.aspx","vetstreet_url":"http://www.vetstreet.com/cats/siberian","vcahospitals_url":"https://vcahospitals.com/know-your-pet/cat-breeds/siberian","temperament":"Curious, Intelligent, Loyal, Sweet, Agile, Playful, Affectionate","origin":"Russia","country_codes":"RU","country_code":"RU","description":"The Siberians dog like temperament and affection makes the ideal lap cat and will live quite happily indoors. Very agile and powerful, the Siberian cat can easily leap and reach high places, including the tops of refrigerators and even doors. ","life_span":"12 - 15","indoor":0,"lap":1,"alt_names":"Moscow Semi-longhair, HairSiberian Forest Cat","adaptability":5,"affection_level":5,"child_friendly":4,"dog_friendly":5,"energy_level":5,"grooming":2,"health_issues":2,"intelligence":5,"shedding_level":3,"social_needs":4,"stranger_friendly":3,"vocalisation":1,"experimental":0,"hairless":0,"natural":1,"rare":0,"rex":0,"suppressed_tail":0,"short_legs":0,"wikipedia_url":"https://en.wikipedia.org/wiki/Siberian_(cat)","hypoallergenic":1}],"id":"WmBbMJmwn","url":"https://cdn2.thecatapi.com/images/WmBbMJmwn.jpg","width":2048,"height":1536}]
~/fujiwara/sample-web-server master
❯ brew install jq
Updating Homebrew...
==> Auto-updated Homebrew!
Updated 1 tap (homebrew/core).
==> New Formulae
swig@3
==> Updated Formulae
pyenv ✔             gibo                lmod                scons
aws-sdk-cpp         glib                mighttpd2           scrcpy
braid               glooctl             minio               ship
calicoctl           gmic                minio-mc            sops
certbot             graph-tool          nomad               telegraf
chakra              gst-plugins-good    opa                 terraform
circleci            hlint               paket               topgrade
envconsul           imagemagick         phpunit             vultr
exiftool            jdupes              procs               webpack
firebase-cli        jfrog-cli-go        pulumi              whois
flow                joplin              pybind11            wildfly-as
fluxctl             knot                rbspy               wtf
folly               libev               scalariform         yelp-tools
==> Deleted Formulae
swig@3.04

==> Installing dependencies for jq: oniguruma
==> Installing jq dependency: oniguruma
==> Downloading https://homebrew.bintray.com/bottles/oniguruma-6.9.2.mojave.bott
==> Downloading from https://akamai.bintray.com/c6/c613befafe81da48913ebd1a7eb03
######################################################################## 100.0%
==> Pouring oniguruma-6.9.2.mojave.bottle.tar.gz
🍺  /usr/local/Cellar/oniguruma/6.9.2: 17 files, 1.3MB
==> Installing jq
==> Downloading https://homebrew.bintray.com/bottles/jq-1.6.mojave.bottle.1.tar.
==> Downloading from https://akamai.bintray.com/71/71f0e76c5b22e5088426c971d5e79
######################################################################## 100.0%
==> Pouring jq-1.6.mojave.bottle.1.tar.gz
🍺  /usr/local/Cellar/jq/1.6: 18 files, 1MB

~/fujiwara/sample-web-server master 26s
❯ curl --silent --request GET --url 'https://api.thecatapi.com/v1/images/search?limit=3' | jq
zsh: correct 'jq' to '_jq' [nyae]? n
[
  {
    "breeds": [],
    "id": "4r2",
    "url": "https://cdn2.thecatapi.com/images/4r2.jpg",
    "width": 717,
    "height": 495
  },
  {
    "breeds": [],
    "id": "dmt",
    "url": "https://cdn2.thecatapi.com/images/dmt.jpg",
    "width": 600,
    "height": 800
  },
  {
    "breeds": [],
    "id": "MTY5NDY5OA",
    "url": "https://cdn2.thecatapi.com/images/MTY5NDY5OA.jpg",
    "width": 1024,
    "height": 679
  }
]

~/fujiwara/sample-web-server master
❯ curl --silent --request GET --url 'https://api.thecatapi.com/v1/images/search?limit=3' > thecat.json

~/fujiwara/sample-web-server master*
❯ curl --silent --request GET --url 'https://api.thecatapi.com/v1/images/search?limit=3'| jq | > thecat.json
zsh: file exists: thecat.json

~/fujiwara/sample-web-server master*
❯ curl --silent --request GET --url 'https://api.thecatapi.com/v1/images/search?limit=3'| jq | > thecats.json

~/fujiwara/sample-web-server master*
❯ cat ~/.bash_profile

# Setting PATH for Python 3.7
# The original version is saved in .bash_profile.pysave
PATH="/Library/Frameworks/Python.framework/Versions/3.7/bin:${PATH}"
export PATH
export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init -)"
export PATH="~/.rbenv/shims:/usr/local/bin:$PATH"
eval "$(rbenv init -)"

~/fujiwara/sample-web-server master*
❯ nodebrew -v
nodebrew 1.0.1

Usage:
    nodebrew help                         Show this message
    nodebrew install <version>            Download and install <version> (from binary)
    nodebrew compile <version>            Download and install <version> (from source)
    nodebrew install-binary <version>     Alias of `install` (For backword compatibility)
    nodebrew uninstall <version>          Uninstall <version>
    nodebrew use <version>                Use <version>
    nodebrew list                         List installed versions
    nodebrew ls                           Alias for `list`
    nodebrew ls-remote                    List remote versions
    nodebrew ls-all                       List remote and installed versions
    nodebrew alias <key> <value>          Set alias
    nodebrew unalias <key>                Remove alias
    nodebrew clean <version> | all        Remove source file
    nodebrew selfupdate                   Update nodebrew
    nodebrew migrate-package <version>    Install global NPM packages contained in <version> to current version
    nodebrew exec <version> -- <command>  Execute <command> using specified <version>

Example:
    # install
    nodebrew install v8.9.4

    # use a specific version number
    nodebrew use v8.9.4

~/fujiwara/sample-web-server master*
❯ nodebrew list
No such file or directory at /usr/local/bin/nodebrew line 575.

~/fujiwara/sample-web-server master*
❯ nodebrew ls
No such file or directory at /usr/local/bin/nodebrew line 575.

~/fujiwara/sample-web-server master*
❯ nodebrew install-binary latest
Fetching: https://nodejs.org/dist/v12.4.0/node-v12.4.0-darwin-x64.tar.gz
Warning: Failed to create the file 
Warning: /Users/tatsuo/.nodebrew/src/v12.4.0/node-v12.4.0-darwin-x64.tar.gz: 
Warning: No such file or directory
                                                                           0.0%
curl: (23) Failed writing body (0 != 1058)
download failed: https://nodejs.org/dist/v12.4.0/node-v12.4.0-darwin-x64.tar.gz

~/fujiwara/sample-web-server master*
❯ cd /

/
❯ ls -a |grep bash

/
❯ ls -a
.                                       Users
..                                      Volumes
.DS_Store                               bin
.DocumentRevisions-V100                 cores
.OSInstallerMessages                    dev
.PKInstallSandboxManager                etc
.PKInstallSandboxManager-SystemSoftware home
.Spotlight-V100                         installer.failurerequests
.file                                   net
.fseventsd                              private
.vol                                    sbin
Applications                            tmp
Library                                 usr
Network                                 var
System

/
❯ nodebrew
nodebrew 1.0.1

Usage:
    nodebrew help                         Show this message
    nodebrew install <version>            Download and install <version> (from binary)
    nodebrew compile <version>            Download and install <version> (from source)
    nodebrew install-binary <version>     Alias of `install` (For backword compatibility)
    nodebrew uninstall <version>          Uninstall <version>
    nodebrew use <version>                Use <version>
    nodebrew list                         List installed versions
    nodebrew ls                           Alias for `list`
    nodebrew ls-remote                    List remote versions
    nodebrew ls-all                       List remote and installed versions
    nodebrew alias <key> <value>          Set alias
    nodebrew unalias <key>                Remove alias
    nodebrew clean <version> | all        Remove source file
    nodebrew selfupdate                   Update nodebrew
    nodebrew migrate-package <version>    Install global NPM packages contained in <version> to current version
    nodebrew exec <version> -- <command>  Execute <command> using specified <version>

Example:
    # install
    nodebrew install v8.9.4

    # use a specific version number
    nodebrew use v8.9.4

/
❯ nodebrew install-binary latest
Fetching: https://nodejs.org/dist/v12.4.0/node-v12.4.0-darwin-x64.tar.gz
Warning: Failed to create the file 
Warning: /Users/tatsuo/.nodebrew/src/v12.4.0/node-v12.4.0-darwin-x64.tar.gz: 
Warning: No such file or directory
                                                                           0.0%
curl: (23) Failed writing body (0 != 1058)
download failed: https://nodejs.org/dist/v12.4.0/node-v12.4.0-darwin-x64.tar.gz

/
❯ nodebrew ls
No such file or directory at /usr/local/bin/nodebrew line 575.

/
❯  mkdir -p ~/.nodebrew/src

/
❯ nodebrew install-binary latest
Fetching: https://nodejs.org/dist/v12.4.0/node-v12.4.0-darwin-x64.tar.gz
######################################################################## 100.0%
Installed successfully

/ 6s
❯ nodebrew ls
v12.4.0

current: none

/
❯ nodebrew use latest
use v12.4.0

/
❯ cd fujiwara
cd: no such file or directory: fujiwara

/
❯ cd

~
❯ cd fujiwara

~/fujiwara master*
❯ cd sample-web-server

~/fujiwara/sample-web-server master*
❯ git add .

~/fujiwara/sample-web-server master*
❯ git commit -m "6/14課題提出"                          

~/fujiwara/sample-web-server master*
❯ git commit -m "6/14 課題提出"
[master eaf63f0] 6/14 課題提出
 3 files changed, 91 insertions(+), 1 deletion(-)
 create mode 100644 thecat.json
 create mode 100644 thecats.json

~/fujiwara/sample-web-server master ⇡
❯ git push -u origin master
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 8 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (5/5), 1.52 KiB | 1.52 MiB/s, done.
Total 5 (delta 0), reused 0 (delta 0)
To github.com:aaabfly/sample-web-server.git
   e137d16..eaf63f0  master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.

~/fujiwara/sample-web-server master
❯ mkdir mywebapi

~/fujiwara/sample-web-server master
❯ cd mywebapi

~/fujiwara/sample-web-server/mywebapi master
❯ npm init
This utility will walk you through creating a package.json file.
It only covers the most common items, and tries to guess sensible defaults.

See `npm help json` for definitive documentation on these fields
and exactly what they do.

Use `npm install <pkg>` afterwards to install a package and
save it as a dependency in the package.json file.

Press ^C at any time to quit.
package name: (mywebapi) 
version: (1.0.0) 
description: 
entry point: (index.js) 
test command: 
git repository: 
keywords: 
author: 
license: (ISC) 
About to write to /Users/tatsuo/Documents/fujiwara/sample-web-server/mywebapi/package.json:

{
  "name": "mywebapi",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC"
}


Is this OK? (yes) 

~/fujiwara/sample-web-server/mywebapi master* 17s
❯ ls
package.json

~/fujiwara/sample-web-server/mywebapi master*
❯ npm install --save express
npm notice created a lockfile as package-lock.json. You should commit this file.
npm WARN mywebapi@1.0.0 No description
npm WARN mywebapi@1.0.0 No repository field.

+ express@4.17.1
added 50 packages from 37 contributors and audited 126 packages in 3.245s
found 0 vulnerabilities


~/fujiwara/sample-web-server/mywebapi master*
❯ sudo code . index.js
Password:

~/fujiwara/sample-web-server/mywebapi master*
❯ ls
node_modules      package-lock.json package.json

~/fujiwara/sample-web-server/mywebapi master*
❯ node index.js
Listening on port 3000
^C

~/fujiwara/sample-web-server/mywebapi master* 48s
❯ node index.js
Listening on port 3000


```
