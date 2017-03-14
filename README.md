# xpath-checker
## usage

Please imitate the `github` config from `etc/default.ini` to create your own config.

```
Usage: bin/xpath-checker [options] [args] ...

--config    <ARG>       : get xpath & header from config
 -c         <ARG>         eg. : userconf/section1
                                userconf/section2
                                section1    equals to default/section1

--xpath     <ARG>       : get xpath from cmd
 -x         <ARG>

--remote    <ARG>       : set remote resource
 -r         <ARG>

--local     <ARG>       : set local resource
 -l         <ARG>

--help                  : display this usage
 -h
```

## demo

### parse from remote url
```
./xpath-checker -c github -r https://github.com/leojin
```
### parse from local file
```
./xpath-checker -c github -l /home/work/tmp/leojin
```
### use personal config file
```
./xpath-checker -c personal_file/personal_section -r https://github.com/leojin
```
### use xpath from command
```
./xpath-checker -x 'id("js-pjax-container")/div/div[1]/a/img/@src' -r https://github.com/leojin
```

## result
```
[work@local001 bin]$ ./xpath-checker -c github -r https://github.com/leojin
----- remote|https://github.com/leojin -----

-- name : name
-- xpath : id("js-pjax-container")/div/div[1]/div[2]/h1/span[2]/text()
-- result: 
['leojin']

-- name : icon
-- xpath : id("js-pjax-container")/div/div[1]/a/img/@src
-- result: 
['https://avatars3.githubusercontent.com/u/6903906?v=3&s=460']
```
