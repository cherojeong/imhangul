# imhangul #
GTK+ 에서 한글을 입력할 수 있게 해주는 입력 모듈입니다.
gtk+-2.0부터는 여러가지 언어의 입력을 처리하기 위해서 입력 모듈이라는 것을 만들었습니다.
이중 한글 입력을 위한 입력 모듈을 따로 구현한 것입니다. 이 것을 설치하고 나서는 gtk+
프로그램에서는 공통으로 한글 입력이 가능해집니다.


## 기능 ##
  * 지원하는 자판: [두벌식](http://libhangul.googlecode.com/git/doc/html/group__hangulkeyboards.html#layout_2) [두벌식 옛글](http://libhangul.googlecode.com/git/doc/html/group__hangulkeyboards.html#layout_2y) [세벌식390](http://libhangul.googlecode.com/git/doc/html/group__hangulkeyboards.html#layout_390) [세벌식최종](http://libhangul.googlecode.com/git/doc/html/group__hangulkeyboards.html#layout_3f) [세벌식순아래](http://libhangul.googlecode.com/git/doc/html/group__hangulkeyboards.html#layout_3s) [세벌식옛글](http://libhangul.googlecode.com/git/doc/html/group__hangulkeyboards.html#layout_3y) [로마자](http://libhangul.googlecode.com/git/doc/html/group__hangulkeyboards.html#layout_ro) [안마태](http://libhangul.googlecode.com/git/doc/html/group__hangulkeyboards.html#layout_ahn)

  * 따로 입력기 프로세스가 작동하지 않고 plugin 방식으로 작동하므로 오버헤드가 적습니다.
  * 한글 조합과 한자 변환을 위한 내부 구현은 [libhangul](http://code.google.com/p/libhangul)을 사용하고 있습니다.


## 설치 방법 ##
많은 배포판에서 이미 imhangul의 바이너리 패키지를 제공하고 있으니 직접 빌드하지 마시고 각 배포판의 바이너리를 찾아서 설치하시기 바랍니다. GTK+ 3.0이 나온후로는 imhangul도 GTK 버젼에 맞게 두 가지를 제공하므로 사용하시는
GTK+ 버전에 맞게 설치하시기 바랍니다.
  * debian gtk2용: apt-get install imhangul-gtk2
  * debian gtk3용: apt-get install imhangul-gtk3

여기서 배포하는 소스는 중 imhangul-2.X.X는 GTK+ 2.0용이고, imhangul-3.X.X는 GTK+ 3.0용 입니다.

## 빌드 방법 ##
```
 $ ./configure --with-default-keyboard=2
 $ make
 # make install
```

## 설정 방법 ##
imhangul을 기본 입력기로 사용하기 위해서는 GTK\_IM\_MODULE이라는 환경 변수를 설정해야 합니다.
GTK\_IM\_MODULE을 다음과 같은 값으로 설정하면 됩니다.
  * hangul2 : [두벌식](http://libhangul.googlecode.com/git/doc/html/group__hangulkeyboards.html#layout_2)
  * hangul2y : [두벌식 옛글](http://libhangul.googlecode.com/git/doc/html/group__hangulkeyboards.html#layout_2y)
  * hangul39 : [세벌식390](http://libhangul.googlecode.com/git/doc/html/group__hangulkeyboards.html#layout_390)
  * hangul3f : [세벌식최종](http://libhangul.googlecode.com/git/doc/html/group__hangulkeyboards.html#layout_3f)
  * hangul3s : [세벌식순아래](http://libhangul.googlecode.com/git/doc/html/group__hangulkeyboards.html#layout_3s)
  * hangul3y : [세벌식옛글](http://libhangul.googlecode.com/git/doc/html/group__hangulkeyboards.html#layout_3y)
  * hangulro : [로마자](http://libhangul.googlecode.com/git/doc/html/group__hangulkeyboards.html#layout_ro)
  * hangulahn : [안마태](http://libhangul.googlecode.com/git/doc/html/group__hangulkeyboards.html#layout_ahn)

## 버그 리포트 ##
http://code.google.com/p/imhangul/issues/list

## GTK+의 버그 ##
GTK+의 구현은 preedit string을 잃어버리기 쉽게 되어 있다.
거기다가 각 언어별로 preedit string을 어떻게 할지 동작 방식이 다르다.
https://bugzilla.gnome.org/show_bug.cgi?id=62948
https://bugzilla.gnome.org/show_bug.cgi?id=643546




