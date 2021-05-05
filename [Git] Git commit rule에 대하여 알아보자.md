# Git commit rule 에 대하여 알아보자

2021.05.05는, 이전까지는 막연한 취미였던 개발을 업으로 먹고 살겠다는 꿈으로 삼은 첫날임과 동시에 1일 1커밋 챌린지를 시작하게 된 날이다. 지금까지는 내가 공부해보고 싶었던 분야, 프로젝트들을 입맛대로 하나씩 줏어먹었다면, 이제부터는 기존에 신경쓰지 않았던 디테일한 부분을 기초부터 쌓아 올라가려 한다. 

Commit rule에 대해서는 그런게 있지.. 정도로만 생각하고 있던 것이 사실이다. 하지만, 1일 1커밋의 시작이 `1 day 1 commit start!` 면 첫인상이 너무 별로지 않겠는가? 하여 지금까지는 내 입맛대로 했던 커밋부터 `제대로` 알아보기로 마음먹었다.

---



#### #1. 커밋의 기본 구조

```
<type>(<scope>): <subject>
<BLANK LINE>
<optional body>
<BLANK LINE>
<optional footer>
```



#### #2. **type** 은 다음 7가지 중 하나여야 한다.

-   **feat**: 새로운 기능(**feat**ure) 추가
-   **fix**: 버그 수정(**fix**)
-   **docs**: 문서(**docs**) 수정
-   **style**: 코드 formatting (**style**), 세미콜론 누락, 코드 변경이 없는 경우
-   **refactor**: 코드 리팩토링(**refactor**ing)
-   **test**: 테스트(**test**) 코드 추가
-   **chore**: 직역하면 잡일(**chore**)들. package manager config 등 프로덕션 코드의 변경 없는 경우.



#### #3. **subject** 는 

-   50글자를 넘지 말아야 한다.

    -   *Tip: If you’re having a hard time summarizing, you might be committing too many changes at once. Strive for [atomic commits](https://www.freshconsulting.com/atomic-commits/) (a topic for a separate post).*

-   (영문 기준) 대문자로 시작해야 하고 마침표로 끝내서는 안된다. 

    -   ~~(기초영문법?)~~ 비단 commit에만 해당되는 내용은 아니다. 

-   (영문 기준) 명령문을 사용하고 과거시제를 사용하지 않는다.

    -   이것은 git의 Built-in Convention을 그대로 따르는 의미를 가진다. 다음 예문을 보면 이해하기 쉽다.

        `git merge` 입력 시

        ```bash
        Merge branch 'myfeature'
        ```

        

        `git revert` 입력 시

        ```bash
        Revert "Add the thing with the stuff"
        
        This reverts commit cc87791524aedd593cff5a74532befe7ab69ce9d.
        ```

-   (한글 기준) 문장보단 구문을 선호한다.
    -   `인증 메소드 고쳐라` → `인증 메소드 수정`



#### #4. body는

-   설명이 필요한 경우만 작성한다.
-   무엇이(What), 왜(Why) 필요한지를 설명한다. How에 관해서는 하지 않는다.
-   한 줄에 72자를 넘어서는 안 된다.



#### #5. Footer는

-   body 와 마찬가지로 선택사항이며 issure tracker ID를 참조하기 위해 사용한다.



#### 예시

````
feat: Summarize changes in around 50 characters or less

More detailed explanatory text, if necessary. Wrap it to about 72
characters or so. In some contexts, the first line is treated as the
subject of the commit and the rest of the text as the body. The
blank line separating the summary from the body is critical (unless
you omit the body entirely); various tools like `log`, `shortlog`
and `rebase` can get confused if you run the two together.

Explain the problem that this commit is solving. Focus on why you
are making this change as opposed to how (the code explains that).
Are there side effects or other unintuitive consequences of this
change? Here's the place to explain them.

Further paragraphs come after blank lines.

 - Bullet points are okay, too

 - Typically a hyphen or asterisk is used for the bullet, preceded
   by a single space, with blank lines in between, but conventions
   vary here

If you use an issue tracker, put references to them at the bottom,
like this:

Resolves: #123
See also: #456, #789
````



#### Reference

-   <a href="https://udacity.github.io/git-styleguide/">Udacity Git Commit Message Style Guide</a>
-   <a href="https://chris.beams.io/posts/git-commit/">Chris Beams - How to Write a Git Commit Message</a>
-   <a href="https://djkeh.github.io/articles/How-to-write-a-git-commit-message-kor/">좋은 git 커밋 메시지를 작성하기 위한 8가지 약속</a>

