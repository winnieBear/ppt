## 最佳实践


## 日常开发推荐
1. Master上和线上保持一致
2. 有需求时，基于master开dev分支和release分支，在dev分支上开发和自测，release用于提测
3. 提测时，release合并dev分支上的修改，提测
4. 提测期间，如果要fix本次提测的bug就在dev上修改，自测，第二次测试时，再把dev上的修改merge到release上，进行第二轮提测；
5. release上的代码测试通过，上线之后，确认没问题，同步release代码到master上，master跟线上再次保持一致；
