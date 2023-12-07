# Google 스타일 가이드

모든 주요 오픈소스 프로젝트에는 스타일 가이드(해당 프로젝트의 코드를 작성하는 방법에 대한 일련의 규칙)가 있습니다. 모든 코드가 일관된 스타일로 작성되어 있어 대규모 코드베이스를 훨씬 더 쉽게 이해할 수 있습니다.

스타일은 "변수 이름은 카멜케이스 사용하기"부터 "전역 변수 사용하지 않기", "예외를 사용하지 않기"에 이르기까지 많은 부분을 다룹니다. 이 프로젝트([google/styleguide](https://github.com/google/styleguide))는 Google 코드에서 우리가 사용하는 스타일 가이드라인입니다. Google에서 시작된 프로젝트를 수정하려면, 아래 페이지로 이동하여 해당 프로젝트에 사용하는 스타일 가이드를 확인할 수 있습니다.

- [AngularJS Style Guide(원문)](https://google.github.io/styleguide/angularjs-google-style.html)
- [Common Lisp Style Guide(원문)](https://google.github.io/styleguide/lispguide.xml)
- [C++ Style Guide(원문)](https://google.github.io/styleguide/cppguide.html)
- [C# Style Guide(원문)](https://google.github.io/styleguide/csharp-style.html)
- [Go Style Guide(원문)](https://github.com/google/styleguide/blob/gh-pages/go)
- [HTML/CSS Style Guide(번역)](./html-css-guide.md)
- [JavaScript Style Guide(원문)](https://google.github.io/styleguide/jsguide.html)
- [Java Style Guide(원문)](https://google.github.io/styleguide/javaguide.html)
- [Objective-C Style Guide(원문)](https://github.com/google/styleguide/blob/gh-pages/objcguide.md)
- [Python Style Guide(원문)](https://google.github.io/styleguide/pyguide.html)
- [R Style Guide(원문)](https://google.github.io/styleguide/Rguide.html)
- [Shell Style Guide(원문)](https://google.github.io/styleguide/shellguide.html)
- [Swift Style Guide(원문)](https://google.github.io/swift/)
- [TypeScript Style Guide(원문)](https://google.github.io/styleguide/tsguide.html)
- [Vim script Style Guide(원문)](https://google.github.io/styleguide/vimscriptguide.xml)

이 프로젝트는 스타일 가이드를 준수하도록 돕는 도구인 [cpplint](https://github.com/google/styleguide/tree/gh-pages/cpplint)와 Google 스타일 Emacs 설정 파일인 [google-c-style.el](https://raw.githubusercontent.com/google/styleguide/gh-pages/google-c-style.el)도 포함되어 있습니다.

프로젝트에서 새로운 XML 문서를 만들어야 하는 경우, [XML 문서 형식 스타일 가이드](https://google.github.io/styleguide/xmlstyle.html)가 도움이 될 수 있습니다. 이 가이드에는 실제 스타일 규칙 외에도 직접 설계하는 것 vs 기존 형식을 적용하는 것, XML 인스턴스 문서 형식, 요소(elements) vs 속성(attributes)에 대한 조언도 포함되어 있습니다.

이 프로젝트의 스타일 가이드는 CC-By 3.0 라이선스를 따르며, 이 문서를 공유할 것을 권장합니다. 자세한 내용은 https://creativecommons.org/licenses/by/3.0/ 을 참조하세요.

Dart에 대한 Google 스타일 가이드는 외부 프로젝트에 있습니다: [Effective Dart](https://www.dartlang.org/guides/language/effective-dart).

## Contributing 기여
몇 가지 예외를 제외하고, 이 스타일 가이드는 Google의 오픈 소스 프로젝트에서 작업하는 개발자를 돕기 위한 Google 내부 스타일 가이드의 사본입니다. 스타일 가이드의 변경 사항은 먼저 내부 스타일 가이드에 적용되고 최종적으로 이 프로젝트에 복사됩니다. **외부 기여는 허용되지 않습니다**. 풀 리퀘스트는 정기적으로 코멘트 없이 마감됩니다. 의문을 제기하거나, 기술적인 측면에서 변경을 추천하거나, 명백한 실수를 지적하는 이슈로 참여하여 변경으로 이어질 수 있지만, 주로 Google 내부의 필요에 맞춰 최적화하고 있습니다.
