# CocoaPods 유용한 정보 모음입니다.
[![License](http://img.shields.io/badge/License-MIT-green.svg?style=flat)](https://github.com/clintjang/cocoapods-tips/blob/master/LICENSE) [![CocoaPods tips](https://img.shields.io/badge/CocoaPods-Tips-orange.svg?style=flat)](https://cocoapods.org/) [![Swift 4](https://img.shields.io/badge/Swift-4.0-orange.svg?style=flat)](https://swift.org) 

[CocoaPods](https://cocoapods.org/)를 감사하게 사용하고 있습니다. 😁<br />
사용하면서 유용했던 정보들을 잘 정리해 두고 싶어서 작성했습니다.<br />
계속 잘 정리해서 처음 사용하시는 분들 혹은 익숙하지 않은 분들에게 도움이 될 수 있도록 하겠습니다. 😊
- 기본적인 설치, 프로젝트 실행에서 유용한 팁까지 정리해봅니다.
- 내부에 모듈화 시켜서 사용하는 셈플도 메모하면서 넣어둘 예정입니다.
> CocoaPods는 Swift 및 Objective-C 프로젝트의 라이브러리 관리자입니다. 45,000 개가 넘는 라이브러리가 있으며 300 만 개가 넘는 App에 사용됩니다. CocoaPod는 프로젝트에서 편리하게 라이브러리를 사용하는 데 도움을 줄 것입니다.

- iOS에서는 추가로 Carthage(카르타고) 라는 비슷한 방식도 있습니다. 워크스페이스를 만드는 방식이 아닌 Embbed Framework를 이용하는 방식이죠.
- android에서의 Maven, Gradle 과 비슷하게 생각하시면 됩니다.
<br /><br />
>> 단, 너무 무분별할 라이브러리 사용은 지양합시다. <br />
자신이 감당할 수 있는 수준으로 사용합시다. <br />
swift는 버전이 계속 변하고 있습니다. 만약 라이브러리 개발하신 분께서 업데이트가 늦거나 업데이트를 하지 않는 상황이 왔을 때, 그걸 대응할 자신이 있어야겠죠?

<br /><br />

## 목차
[# 기본적인 설치방법](https://github.com/ClintJang/cocoapods-tips#-기본적인-설치방법)<br />

[# 프로젝트 생성과 초기셋팅방법](https://github.com/ClintJang/cocoapods-tips#-프로젝트-생성과-초기셋팅방법)<br />

[# 맥용 프로그램](https://github.com/ClintJang/cocoapods-tips#-맥용-프로그램)
<br />

[# 팟 셋팅이 꼬였을때](https://github.com/ClintJang/cocoapods-tips#-팟-셋팅이-꼬였을때)
<br />

[# 저장소별 무시 목록 작성하기](https://github.com/ClintJang/cocoapods-tips#-저장소별-무시-목록-작성하기)
<br />
<br />

> 터미널 명령어

[#1-1 버전정보 확인하기](https://github.com/ClintJang/cocoapods-tips#1-1-버전정보-확인하기)<br />

[#1-2 최신버전으로 업데이트 하기](https://github.com/ClintJang/cocoapods-tips#1-2-최신버전으로-업데이트-하기)<br />

[#1-3 버전 바꾸기](https://github.com/ClintJang/cocoapods-tips#1-3-버전-바꾸기)<br />

[#1-4 환경정보 보기](https://github.com/ClintJang/cocoapods-tips#1-4-환경정보-보기)<br />
<br />

> Podfile 작성 팁

[#2-1 def 사용](https://github.com/ClintJang/cocoapods-tips#2-1-def-사용)<br />

[#2-2 Debugging 에서만 사용하기](https://github.com/ClintJang/cocoapods-tips#2-2-Debugging-에서만-사용하기)<br />

[#2-3 git의 repository에서 직접 가져오기](https://github.com/ClintJang/cocoapods-tips#2-3-git의-repository에서-직접-가져오기)<br />

[#2-4 xcode에서 pods 프로젝트 경고 없애기](https://github.com/ClintJang/cocoapods-tips#2-4-xcode에서-pods-프로젝트-경고-없애기)<br />

<br />
<br />

> 코코아팟츠에 자신의 라이브러리 등록하기

[#3-1 코코아팟츠에 자신의 라이브러리 등록해본 과정](https://github.com/ClintJang/cocoapods-tips#3-1-코코아팟츠에-자신의-라이브러리-등록해본-과정)<br />

<br />
<br />


## [# 기본적인 설치방법](https://guides.cocoapods.org/using/getting-started.html)

> Ruby gem이 필요합니다. CocoaPods는 Ruby로 제작되었으며 macOS에서 사용할 수있는 기본 Ruby로 설치할 수 있습니다. 


cocoapods 를 설치합니다.
```
$ sudo gem install cocoapods
```

설치 후에 setup을 실행해서 CocoaPods master repo 를 설정합니다.
- setup : Setup the CocoaPods environment 이라 적혀있네요. 
- 필요한 파일을 다운로드해서 Pods를 이용할 준비를 합니다.
```
$ pod setup
```

기본적인 사용을 위한 설정을 완료했습니다. 이제 xcode에 라이브러리 설치가 가능합니다.
초기 프로젝트, Pods 최신버전, 베타버전, 버전 변경은 아래에서 확인해주세요.

[Top으로 가기](https://github.com/ClintJang/cocoapods-tips#목차)

## [# 프로젝트 생성과 초기셋팅방법](https://guides.cocoapods.org/using/using-cocoapods.html)

1. 프로젝트를 생성합니다.
2. 프로젝트의 해당 폴더로 이동합니다.
	1. 프로젝트.xcodeproj 파일이 있는 폴더로 이동합니다.

```
$ cd 프로젝트경로 
```
3. Podfile 파일을 생성합니다.
```
$ pod init
```

4. Podfile 파일을 편집합니다.
	1. 능력 것 편집 합니다. (tool 이나 vi 등등)
```
target '프로젝트명' do
  # 스위프트를 사용하지 않고 동적 라이브러리를 이용하지 않는다면 아래 구문을 주석처리 합니다
  use_frameworks!

  # 대표적인 네트워크 라이브러리입니다.
  pod 'Alamofire'

  # 스넵킷이라는 오토레이아웃을 소스 코드 구현을 용이하게 해주는 라이브러리입니다.
  pod 'SnapKit'
end
```

5. 참고로 지원하는 라이브러리가 있는지 찾아 볼때?
```
$ pod search 라이브러리명
```
 
6. Pod를 이용해서 라이브러리 설치하기
```
$ pod install
```
7. 만들어진 워크스페이스 파일 실행
	1. 콜솔 명령어가 아닌 그냥 파일을 찾아 실행하면 됩니다.
```
$ . 프로젝트명.xcworkspace
```
- or 그냥 클릭으로 프로젝트명.xcworkspace 파일 실행 

<img width="280" height="135" src="/Image/xcworkspace_ok.png"></img>

[Top으로 가기](https://github.com/ClintJang/cocoapods-tips#목차)

## [# 맥용 프로그램](https://cocoapods.org/app)

- 다운로드 링크 : https://cocoapods.org/app
	1. 제일 밑으로 스크롤 하면 하단에 "Download CocoaPods.app" 라는 버튼이 있습니다.
	2. 클릭하면 최신 버전의 프로그램을 받을 수 있습니다.

GUI에서 Podfile 관리와 Pod Install, Update가 가능합니다.
- 이미지로 보면? 실행했을 때 시작화면입니다.

<img width="366" height="322" src="/Image/cocoapodsApp00.png"></img>

[Top으로 가기](https://github.com/ClintJang/cocoapods-tips#목차)

## [# 팟 셋팅이 꼬였을때](https://github.com/ClintJang/cocoapods-tips#-Pod셋팅이-꼬였을때)

이것은 제가 사용하는 방법입니다.
- Podfile 파일이 있는 폴더 기준입니다.
1. Pods 폴더포함 모두 삭제
2. Podfile.lock 파일 삭제
3. 프로젝트명.xcworkspace 파일 삭제
4. 프로젝트명.xcodeproj에 마우스를 올리고 오른쪽 클릭, 아래 진행
	1. 패키지 내용보기
	2. project.pbxproj 과 기타 파일들이 보여질 것입니다.
	3. project.pbxproj만 남기고 다른 파일 모두 삭제
		1. project.pbxproj 파일 1개는 꼭 남기세요.
		2. 나머지는 과감하게 지우세요.

<table style="width:100%">
  <tr>
	<th>삭제 전 프로젝트의 폴더</th> 
    <th>삭제 전 프로젝트 파일의 패키지 내용</th>
  </tr>
  <tr>
  	<td><img width="275" height="84" src="/Image/pod_error_before01.png"></img></td>
    <td><img width="324" height="77" src="/Image/pod_error_before02.png"></img></td>
  </tr>
</table>

<br />

<table style="width:100%">
  <tr>
	<th>삭제 후 프로젝트의 폴더</th> 
    <th>삭제 후 프로젝트 파일의 패키지 내용</th>
  </tr>
  <tr>
  	<td><img width="272" height="58" src="/Image/pod_error_after01.png"></img></td>
    <td><img width="327" height="82" src="/Image/pod_error_after02.png"></img></td>
  </tr>
</table>

5. Podfile이 있는 폴더에서 다시 Install Or Update 실행
	1. 전 보통 Install을 합니다.

```
$ pod install
or
$ pod update
```


6. 만들어진 프로젝트명.xcworkspace를 실행해서 확인합니다.


[Top으로 가기](https://github.com/ClintJang/cocoapods-tips#목차)

## [# 저장소별 무시 목록 작성하기](https://github.com/ClintJang/cocoapods-tips#-저장소별-무시-목록-작성하기)

.gitignore 파일을 생성해 두면 편리합니다. <br />
.gitignore 파일이란 Git 버전 관리에서 제외할 파일 목록을 지정하는 파일입니다.<br />
. 표시는 숨김파일을 의미합니다.<br />
```
Finder에서 아래 단축키를 사용하면 숨겨진 파일이 보여집니다.

단축키 : shift +command + .
```

git 파일이 있는 최상위 디렉토리에서 터미널을 실행시켜 내용을 작성합니다.

1. .gitignore 파일을 생성한다.
```
$ touch .gitignore 
```
2. 만들어졌는 지 확인한다면? 
```
$ ls -a 
```
3. 편한 방법으로 해당 파일을 편집합니다.
```
$ vi .gitignore
```

내용의 셈플을 [샘플 .gitignore](https://github.com/ClintJang/cocoapods-tips/blob/master/.gitignore)은 아래와 같습니다.
- .gitignore
```
# Pods 관련 (pod install or pod update 해서 자동 생성된 파일들) 
Podfile.lock
JWSCocoapodsTips.xcworkspace	
JWSCocoapodsTips/Pods/			

# xcodeproj 안의 불필요파일
*.xcuserstate
xcschememanagement.plist
contents.xcworkspacedata

# 필요한 내용 더 추가 
```

4. 설정이 되면 이제 git commit 할때 관련 불필요한 파일은 나타나지 않을거에요~


[Top으로 가기](https://github.com/ClintJang/cocoapods-tips#목차)

<br />
<br />

## [#1-1 버전정보 확인하기](https://github.com/ClintJang/cocoapods-tips#1-1-버전정보-확인하기)


버전을 확인합니다.

```
$ pod —-version
```

Gems 의 상세한 버전을 원할 경우 입니다.
```
$ gem which cocoapods
```

[Top으로 가기](https://github.com/ClintJang/cocoapods-tips#목차)

## [#1-2 최신버전으로 업데이트 하기](https://github.com/ClintJang/cocoapods-tips#1-2-최신버전으로-업데이트-하기)


최신버전으로 설치합니다.

```
$ [sudo] gem install cocoapods --pre
```
[Top으로 가기](https://github.com/ClintJang/cocoapods-tips#목차)

## [#1-3 버전 바꾸기](https://github.com/ClintJang/cocoapods-tips#1-3-버전-바꾸기)

제거하고 설치를 하려면 아래와 같이 하면 됩니다.
1. 먼저, 삭제합니다.

```
$ [sudo] gem uninstall cocoapods
```

2. 원하는 버전으로 설치합니다.

```
$ [sudo] gem install cocoapods -v 1.3.1
```

<br />

pods가 설치되어있고, 바로 버전을 바꾸고 싶다면!
```
$ pod _1.3.1_ setup
```

[Top으로 가기](https://github.com/ClintJang/cocoapods-tips#목차)

## [#1-4 환경정보 보기](https://github.com/ClintJang/cocoapods-tips#1-4-환경정보-보기)

Pod 설정 정보가 보고 싶다면
1. 임의 경로에서 실행
	1. Stack : CocoaPods버전, Ruby버전, RubyGems버전, Xcode 버전, Git버전, Ruby lib경로, Repositories 등등.. 여러 정보를 확인할 수 있습니다.
	2. Installation Source : pod 설치 경로
	3. Plugins : 관련 플러그인 정보
```
$ pod env
```

2. Podfile이 있는 경로에서 실행
	1. 1번의 내용에 이어서 Podfile 정보도 같이 출력됩니다.
```
$ cd 프로젝트경로
$ pod env
```

[Top으로 가기](https://github.com/ClintJang/cocoapods-tips#목차)

<br />
<br />

## [#2-1 def 사용](https://github.com/ClintJang/cocoapods-tips#2-1-def-사용)


아래와 같이 def-end 를 이용해서 사전 정의된 값을 가져와서 사용할 수 있습니다.
- 재사용성과 깔끔한 정리~

```
def network_pods

  # 대표적인 네트워크 라이브러리입니다.
  pod 'Alamofire'
  # Alamofire를 사용할 때 상단 상태 바에 통신중일때 기본 인디케이터가 나타나도록 합니다.
  pod 'AlamofireNetworkActivityIndicator'
  # Alamofire를 이용할 때 로그를 쉽게 볼 수 있습니다.
  pod 'AlamofireActivityLogger'
end

def core_pods

  # 스넵킷이라는 오토레이아웃을 소스 코드 구현을 용이하게 해주는 라이브러리입니다.
  pod 'SnapKit'
  
  # 유용한 날짜 관련 라이브러리입니다.
  pod 'SwiftDate'
end

target '프로젝트명' do
  # 스위프트를 사용하지 않고 동적 라이브러리를 이용하지 않는다면 아래 구문을 주석처리 합니다
  use_frameworks!

  # 이렇게 위에 정의된 내용을 사용합니다.
  network_pods
  core_pods
end
```
[Top으로 가기](https://github.com/ClintJang/cocoapods-tips#목차)

## [#2-2 Debugging 에서만 사용하기](https://github.com/ClintJang/cocoapods-tips#2-2-Debugging-에서만-사용하기)

Debugging-에서만-사용하기

```
pod '라이브러리명', :configurations => ['Debug']
```
or 다른 옵션도 가능하죠.

```
pod '라이브러리명', '~> 4.0', :configurations => ['Debug']
```
[Top으로 가기](https://github.com/ClintJang/cocoapods-tips#목차)

## [#2-3 git의 repository에서 직접 가져오기](https://github.com/ClintJang/cocoapods-tips#2-3-git의-repository에서-직접-가져오기)

git에 직접 접근해서 가져오기

```
pod '라이브러리명', :git => 'https://github.com/라이브러리경로'
```
or 그 안의 브런치의 최신 라이브러리가 필요하다면

```
pod '라이브러리명', :git => 'https://github.com/라이브러리경로', :branch => '브런치명'
```
or tag 정보까지의 라이브러리가 필요하다면?

```
pod '라이브러리명', :git => 'https://github.com/라이브러리경로', :tag => '1.0.0'
```

or 원하는 commit된 부분까지가 필요하다면?

```
pod '라이브러리명', :git => 'https://github.com/라이브러리경로', :commit => '0e380832ab'
```

[Top으로 가기](https://github.com/ClintJang/cocoapods-tips#목차)

<br />
<br />

## [#2-4 xcode에서 pods 프로젝트 경고 없애기](https://github.com/ClintJang/cocoapods-tips#2-4-xcode에서-pods-프로젝트-경고-없애기)

Podfile에서 "inhibit_all_warnings!" 만 추가하면 간단하게 경고가 사라집니다.
1. inhibit_all_warnings! 코드 추가 
```

target '프로젝트명' do
  # 스위프트를 사용하지 않고 동적 라이브러리를 이용하지 않는다면 아래 구문을 주석처리 합니다
  use_frameworks!
  
  # xcode에서 pods의 모든 프로젝트 경고 없애기
  inhibit_all_warnings!

end
```

or 라이브러리 별로(개별로).., 원하는 라이브러리만 경고를 사라지게 하고 싶다면?

```
pod '라이브러리명', :inhibit_warnings => true
```

2. pod install을 다시 하고
```
$ pod install
```

3. 빌드실행
> 빌드는 워크스페이스 파일을 실행해서 xcode에서 해야죠~ 

- 테스트해 본 상세 내용 : [링크 클릭!](https://github.com/ClintJang/cocoapods-tips/blob/master/JWSCocoapodsTips/Podfile)


[Top으로 가기](https://github.com/ClintJang/cocoapods-tips#목차)

<br />
<br />

## [#3-1 코코아팟츠에 자신의 라이브러리 등록해본 과정](https://github.com/ClintJang/cocoapods-tips#3-1-코코아팟츠에-자신의-라이브러리-등록해본-과정)
> 2017년 10월 18일 테스트 진행했던 과정을 정리한 것입니다.

참고한 유튜브 동영상 링크 : https://www.youtube.com/watch?v=gNMNeqXKnzw

- 참고한 링크 1 : https://guides.cocoapods.org/making/index.html
- 참고한 링크 2 : https://magi82.github.io/ios-regist-cocoapods/

코코아팟츠는 설치되어있을 거라는 가정하게 아래는 진행사항입니다.

```
# Go Go!
1. pod lib create 프로젝트명 : Demo Application이 생성된다.
 - http://guides.cocoapods.org/making/using-pod-lib-create.html : 여기를 참고 하라고 알려줌
 - 질문에 답은.. swfit, yes, none, no.. 통상 이리 하게 된다. 처음에 저도 같은 선택을 했음.
2. 그리고 github에 프로젝트를 생성한다.
3. 이후 터미널에서 생성한 레파지토리에 프로젝트를 추가한다.

…or create a new repository on the command line

echo "# 프로젝트명" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/ClintJang/프로젝트명.git
git push -u origin master
…or push an existing repository from the command line

git remote add origin https://github.com/ClintJang/프로젝트명.git
git push -u origin master

.. 실제
3.1. cd 프로젝트명의 폴더
3.2. git remote add origin https://github.com/ClintJang/프로젝트명.git
3.3. git add .
3.4. git commit -m "Create project via pod"
3.5. git push -u origin master
3.6. 잘 올라갔는 지 레파지 토리 확인

4. 다시 example의 xcode 실행파일로 돌아와서 Podspec Metadata폴더안의 프로젝트명.podspec를 수정한다.

5. pod lib lint 프로젝트명.podspec : 오류가 있는 지 검증한다.

5.1. pod lib lint --verbose : 과정을 보려면
5.2. pod lib lint --verbose --no-clean : 클린 빌드 하려면
5.3. pod lib lint --allow-warnings : 경고는 무시하려면

5.4. 프로젝트 passed validation : 이 메시지를 봐야된다.
5.4.1. 잘 되었는 지 확인은 다른 프로젝트에서 pod를 추가해 보면 된다.
5.4.2. podfile에 pod '프로젝트명', :path => '경로/경로/프로젝트명'
5.4.3. 해당 콘솔에서 pod install

6. git status : 반영할 것이 있는 지 확인한다.
6.1. git add . : 추가
6.2. git status :  녹색 확인
6.3. git commit -m "해당 수정내역"
6.4. git status : 이젠 없을 것임...

7. git tag 0.1.0 -a 버전 정보를 맞춘다. 
7.1. 작성할 내용 추가하고 esc :x로 나온다.
7.1.1. 귀찮으면 git tag 0.1.0 : 까지 한다.
7.2. git status 로 상태를 확인한다. push 할 것이 있을 것이다...
7.3. 혹은 그냥 github site에서 release Tap을 찾아서 거기서 직접 작성해서 같은 버전을 추가한다.!!!
7.4. 잘 적용되면 git tag 로 확인 


8. git push --tags
8.1.  * [new tag]         0.1.0 -> 0.1.0 메시지를 확인해야된다.

9. pod trunk register 메일주소 '이름' --description='상세'
9.1. 반드시 메일에서 가서 웹 링크를 클릭해야됩니다!!!!!!! 그리고 

10. pod trunk push
10.1. 경고가 많으시다면... pod trunk push --allow-warnings

아래의 메시지를 보시면 성공!!! (If you see the message below, you will succeed !!!)
 🎉  Congrats

 🚀  프로젝트명("Project Name") (0.1.0) successfully published
 📅  October 18th, 15:34
 🌎  https://cocoapods.org/pods/프로젝트명("Project Name")
 👍  Tell your friends!
 
 
 # end
 - Fun day!
 
```

[Top으로 가기](https://github.com/ClintJang/cocoapods-tips#목차)