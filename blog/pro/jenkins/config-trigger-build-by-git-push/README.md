
# 設定從 Git 觸發 Jenkins 建置

> 此案例完全使用自建環境，即自架 Jenkins Server 和 Bonobo Git Server


## 安裝 Bonobo Git Server ...

### 建立 Repository: `BankTest`
```
https://my.git.server.url/git/BankTest.git
```

### 安裝 curl ( 使用 choco )
```
choco install curl -y
```

### 建立 `post-receive` 檔案
Bonobo Git Server 的預設 Repositories 路徑位於 `~\App_Data\Repositories\`
所以 Repository BankTest 的檔案庫路徑位於 `~\App_Data\Repositories\BankTest\hooks\`
在 hooks 資料夾已經有一預設範例檔案 `README.sample` copy 新檔並更名為: `post-receive`
保留第一行 `#!/bin/sh` 修改內容如下: 
```
#!/bin/sh
echo Notifying Jenkins Server
curl https://my.jenkins.server.url/git/notifyCommit?url=https://my.git.server.url/git/BankTest.git -k
```
> curl ... -k 忽略 SEC_E_UNTRUSTED_ROOT 錯誤，就是自訂憑證警告問題

> 此時 git push 動作會產生 web hook 執行 post-receive 內的指令


## 安裝 Jenkins ...

### 建立 Work Item: `BankTest`

- Source Code Management: Git
  . Repository URL: `https://my.git.server.url/git/BankTest.git`
  . Credentials: ... ( 輸入帳密 )
- Build Triggers: Poll SCM
  > No schedules so will only run due to SCM changes if triggered by a post-commit hook

> 此時已經可以從 git push 觸發 Jenkins 建置 BankTest 動作
