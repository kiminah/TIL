# 원격저장소 push시 오류

* 원격 저장소와 로컬 저장소의 커밋 히스토리를 아래에서 확인하고

  ```bash
  $ git push origin master
  To https://github.com/kiminah/bigdata.git
   ! [rejected]        master -> master (fetch first)
  error: failed to push some refs to 'https://github.com/kiminah/bigdata.git'
  # 거절됨 (rejected)
  # 원격 저장소의 작업(커밋)이 로컬에 없음
  hint: Updates were rejected because the remote contains work that you do
  # 다른 저장소에 푸시하는 경우도 발생 가능
  hint: not have locally. This is usually caused by another repository pushing
  # 원격 저장소의 변경사항을 먼저 통합하고
  # 예) git pull ...
  hint: to the same ref. You may want to first integrate the remote changes
  # 다시 push 
  hint: (e.g., 'git pull ...') before pushing again.
  hint: See the 'Note about fast-forwards' in 'git push --help' for details.
  ```

  * vim 편집기 창이 popup 될것
    * esc + :wq 엔터
      * w : write (저장)
      * q : quit (나가기)

* log를 확인한다

  ```bash
  $ git log --oneline
  # vim 편집지가 뜬 이유 => 합쳐졌다라는 사실을 커밋으로 남김
  30f76d8 (HEAD -> master) Merge branch 'master' of 
  https://github.com/kiminah/bigdata
  # 로컬 작업 한 것
  a81f2d7 Add text.txt
  780a325 (origin/master) Update README.md
  8d24682 Add README.md
  ```

* 다시 push 한다.

  ```bash
  $ git push origin master
  Enumerating objects: 6, done.
  Counting objects: 100% (6/6), done.
  Delta compression using up to 8 threads
  Compressing objects: 100% (4/4), done.
  Writing objects: 100% (4/4), 534 bytes | 534.00 KiB/s, done.
  Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
  To https://github.com/edutak/bigdata.git
     17e362c..833856a  master -> master
  ```

  