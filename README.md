
<font color="#450cc4" size = "3px">	
	
# Reference for Ztool

## How to install

use the follow command to install all the tools.

	git clone https://github.com/peter-m-shi/ztool.git $HOME/ztool;sh $HOME/ztool/setup.sh

use the foloow command to install a special tool.

	sh setup.sh mptools
	
## How to use tools
## gitf命令集
### gitf feature
- ```gitf feature [分支名] go```亦可直接输入```ff [分支名] go```:开始一个新的feature。
- ```gif feature [分支名] pr```亦可直接输入```ff [分支名] pr```：提pull request到develop。
- ```gif feature [分支名] ok```亦可直接输入```ff [分支名] ok```：合并feature到develop，同时删除该feature。
- 示例：
```
$ ff IOS-9-pageRefactor go
$ ff IOS-9-pageRefactor pr
$ ff IOS-9-pageRefactor ok
```

### gitf bugfix
- ```gif bugfix [分支名] go```亦可直接输入```fb [分支名] go```：开始一个新的bugfix。
- ```gif bugfix [分支名] pr```亦可直接输入```fb [分支名] pr```：提交pull request到develop或release。
- ```gif bugfix [分支名] ok```亦可直接输入```fb [分支名] ok```：合并bugfix到develop或release，同时删除该bugfix。
- 示例：
```
$ fb MGV5-20538-ringFail go
$ fb MGV5-20538-ringFail pr
$ fb MGV5-20538-ringFail ok
```

### gitf release
- ```gif release [分支名] go```亦可直接输入```fr [分支名] go```：开始一个新的release。
- ```gif release [分支名] pr```亦可直接输入```fr [分支名] pr```：提交pull request到master和develop。
- ```gif release [分支名] ok```亦可直接输入```fr [分支名] ok```：合并release到master和develop，同时给master打tag，删除该release。
- 示例：
```
$ fr 6.0.0 go
$ fr 6.0.0 pr
$ fr 6.0.0 ok
```

### gitf hotfix
- ```gif hotfix [分支名] go```亦可直接输入```fh [分支名] go```：开始一个hotfix。
- ```gif hotfix [分支名] pr```亦可直接输入```fh [分支名] pr```：提交pull request到master。
- ```gif hotfix [分支名] ok```亦可直接输入```fh [分支名] ok```：合并到master和develop，同时删除该hotfix。
- 示例：
```
$ fh 6.0.1 go
$ fh 6.0.1 pr
$ fh 6.0.1 ok
```

## gitz命令集






#localizable

Use locinit to init configrure in  localizable folder
	
	locinit

Use loc2s to convert xls to strings file
	
	loc2s

Use loc2x to convert strings file to xls
	
	loc2x
	
Use lochelp to show help info
	
	lochelp
	
#package

Change xcode project configuration by gien config file

	pkg -env dev.cfg
	
Build xcode project

	pkg -build

Build xcode project by Debug or Release

	pkg -build Debug
	
Clean xcode project

	pkg -clean
	
Make ipa file

	pkg -make

Batch make ipa file

	pkg -bat

Env configuration
	
	[Use ':' to define Action && Object]
	|							Action							|		Object			  |
	|			Key 		  |flag|			Value 			|subObj|		Obj 	  |
	GCC_PREPROCESSOR_DEFINITIONS++DEBUG=1 INHOUCE_LOC=0 OTHER=1:Widget<-Project.xcodeproj

	Action flag:
	[>>]
	Use 'key>>value' Set key-value in Action: 
	CFBundleIdentifier>>com.company.product

	[++]
	Use 'key++value' add key-value in Action:
	GCC_PREPROCESSOR_DEFINITIONS++A=1 B=3 C=3

	[Object]
	Use 'subObj<-Obj' define target of project:
	Widget<-Project.xcodeproj

	[Object Support Type]
	.plist
	.entitlements
	.xcodeproj
	.file(only format)

Make configuration

1、Defined by action
	
filed|description|remark
:---------------|:---------------	|:---------------
Build Mode| argument used in 'pkg -b [debug/release]'
Build Time| the time when build/make | %Y%m%d%H%M%S

2、Defined in Info.plist

filed|description|remark
:---------------|:---------------	|:---------------
Product Name|Bundle name|String type, etc. "Product"
Product Version|Bundle versions string, short|String type, etc. "6.2.0"
Build Version|Bundle version | Interger type, etc. 620

3、Custom filed defined in Info.plist
	
filed|description|remark
:---------------|:---------------	|:---------------
Product Stage|APP_STAGE|String type, etc. "stage 1"
Git Version|APP_GIT_REVISION
Channel|APP_CHANNEL|String type, etc. "91"
Environment|APP_ENV|Interger type,0-DevEnv 1-TestEnv 2-GreyEnv 3-ReleaseEnv
Custom|APP_CUSTOM|String type, etc. "custom filed"

4、Fields prioprity in ipa name:
	
	{Product Name}\_{Product Version}\_{Build Mode}\_{Product Stage}\_{Build Time}\_{Channel}\_{Environment}\_{Custom}\_{Build Version}\_{Git Version}

5、Enable build version auto increase 

	set CFBundleVersionAutoIncrease=1 in Info.plist

	
#mptools

List all the provisionprofile file

	mplist
	
Remove all the provisionprofile file

	mpclean
	
Install provisionprofile file

	mpinstall test.provisionprofile
	
Install provisionprofile folder

	mpinstall ./provisionprofileFolder

#utility

Quik start project by xcode

	xx
	
Quik start project by appcode

	aa
	
#shell

change shell to zsh

	sh setup.sh
   
