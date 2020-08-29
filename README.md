### iterm2 rz 与 sz

1. 安装 `lrzsz` 命令 `brew install lrzsz`

2. 将 `iterm2-recv-zmodem.sh` 和 `iterm2-recv-zmodem.sh` 保存到 `/usr/local/bin` 目录下

3. 给文件添加可执行权限，一般 `chmod 777` 就可以了
`chmod 777 /usr/local/bin/iterm2-*`

4. 设置 iterm2 的 trigger 特性
`Profiles->Default->EditProfiles->Advanced` 中的 `Tirggers`
添加两条 `Trigger`，分别设置 `Regular expression`，`Action`，`Parameters`，`Instant`，如下所示

```
Regular expression: rz waiting to receive.\*\*B0100
Action: Run Silent Coprocess
Parameters: /usr/local/bin/iterm2-send-zmodem.sh
Instant: checked

Regular expression: \*\*B00000000000000
Action: Run Silent Coprocess
Parameters: /usr/local/bin/iterm2-recv-zmodem.sh
Instant: checked
```
