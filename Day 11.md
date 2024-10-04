# Day 11 - Oct 2, Wed

### What I did:
- [LeetCode October Daily Challenge](https://leetcode.com/problems/rank-transform-of-an-array/description/?envType=daily-question&envId=2024-10-02) 풀기
- Chirpy Theme 7.1.1 업데이트
- HealthKit Sample App(MapKit 관련) 프로토타입 구현하기
  - 필요한 자료 및 앱 조사
  
### Key Learnings:
- [OrderedDictionary](https://github.com/apple/swift-collections/blob/main/Documentation/OrderedDictionary.md) 사용해보기
- 문제가 되었던 eventmachine 설치 [이슈](https://github.com/imjhk03/imjhk03.github.io/issues/215) 해결
  - 이슈 발생
    - 테마 업데이트(bundle update)하는 과정에 eventmachine 라이브러리에서 오류가 계속 발생하여 정상적으로 테마 업데이트 불가능
    - openssl, rvm 등등 필요한 것들을 추가적으로 설치 진행했지만 여전히 오류 발생
    - eventmachine에서 오류 대응하고 나서 정상적으로 업데이트 가능할 것 같아 대기중이었음
  - 이슈 해결
    - openssl, rvm 등 관련 라이브러리들 설치 및 버전 맞춤
      - ruby version 3.3.5
      - 3.2.3 in rbenv
    - MacOS command line tools issue랑 연관 되어 있어서 추가 설정
      - https://talk.jekyllrb.com/t/unable-to-install-jekyll-on-mac-os-10-15/5127/8
      - MacOS 15 fails to build native extensions eventmachine/eventmachine#1009 (comment)
    - eventmachine 따로 설치 후 bundle install 해서 clean install 진행 후 이슈 해결
      ```
      gem install eventmachine -- --with-openssl-dir=$(brew --prefix openssl@3.0)
      bundle install
      ```
  - 이번 이슈로 인해 추가적으로 필요한 라이브러리들도 설치해보고 필요한 부분들도 수정해보면서 좀 더 다양한 경험을 해볼 수 있었음
    - 하지만 한편으로는 버전 업데이트로 인한 추가적인 라이브러리 설치 및 업데이트 과정 이슈 해결에 대한 시간 소요가 걸려,
      웹사이트 페이지에 글을 작성하고 바로 배포할 수 있는 플랫폼으로 전향할까 고민이 되었음

