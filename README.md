# TodayILearned | JeeInho
> 기억보단 기록을

제가 배운것들을 기록하고 설명하기위해 시작한 Challenge 입니다

## Rules
> 적어도 이것만은 지키자
- 자신이 만족할만한 내용을 커밋한다

    _Github 그 어디에도 의미없는 커밋은 없기에_

    나 자신이 만족할정도의 퀄리티를 가진 내용만을 커밋한다.
- 치팅은 하지만 어뷰징은 하지 않는다 (by JeongHoon Byon)

    단 한문장이더라도, 그날 배운내용을 담을 수 있다면 커밋을 해도 상관없다.
    하지만, 커밋 시간을 강제로 변경하거나, 빈 커밋로그를 남기는 등의 잘못된 방식은 사용하지 않는다.
- 고정관념에 빠지지 않는다
    TIL 에는 항상 **배운것들** 만을 적어야 한다고 생각하지 않는다.
    그날 자신이 한것을 자유롭게 작성한다.
## File Structure
> 약간 특이한 TIL, N진 트리형 TIL
- TIL 은 N진 트리 방식으로, 특정 topic 에 대해 작성하고, 이에 연계된 궁금증/할것을 하위노드로 작성합니다
### Topic
web, android 등, TIL 작성에 대한 분야별 분류이다
- Topic 폴더 : Topic 에 대한 소개 및 관련 Issue 들을 저장하는 폴더이다
- ${topicName}.md (Topic 인트로) : 해당 Topic 에 대한 간략한 소개가 작성된 파일이다
### Issue
배우거나 기록할 내용 자체를 말한다
- Issue 폴더 : issue 와 해당 issue 에 대한 하위 issue 를 담는 폴더이다.
- ${issueName}.md (Issue 컨텐츠) : 이슈 내용이 작성된 파일이다
- 하위 Issue 폴더 : 특정 Issue 에 대해 연계되어 작성된 Issue 를 담는 폴더를 뜻한다
### Conventions
- Topic 폴더는 항상 저장소 root 에 있어야한다
- 모든 Topic 폴더내에는 Topic 인트로가 존재해야한다
- Issue 폴더는 하나의 Issue 컨텐츠와 0개 이상의 하위 Issue 폴더를 가져야 한다.
- 하위 Issue 폴더 또한 Issue 폴더로 상정한다 (즉, 하위 Issue 폴더 또한 하나의 Issue 컨텐츠와 0개이상의 하위 Issue 폴더를 가져야 한다)

### Example
```
/web
    web.md
    /http-protocol
        http-protocol.md
        /server-client-model
            server-client-model.md
        /protocol
            protocol.md
    /rest-api
        rest-api.md
/android
    android.md
```

## Contents

**배운것들**
- - -
- [[ROOT | 2021.10.05] HttpProtocol이란?](https://github.com/key-del-jeeinho/TIL/blob/main/web/http-protocol/http-protocol.md)
- [[NODE | 2021.10.06] Client Server Model이란?](https://github.com/key-del-jeeinho/TIL/blob/main/web/http-protocol/client-server-model/client-server-model.md)


**해온것들**
- - -
_내용을 입력해주세요_

![](https://img.shields.io/badge/since-2021.10.05-FA5996)
![](https://img.shields.io/badge/author-JeeInho-5BE1C8)
![](https://img.shields.io/badge/combo-1-0A4DC8)

[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2Fkey-del-jeeinho%2FTIL&count_bg=%2379C83D&title_bg=%23555555&icon=riotgames.svg&icon_color=%23E7E7E7&title=TIL-Challange&edge_flat=false)](https://hits.seeyoufarm.com)

