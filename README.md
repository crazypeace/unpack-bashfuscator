# unpack-bashfuscator

```
exec 3> bashx.log; BASH_XTRACEFD=3 bash -x encoded.sh
```

得到最终的解密结果为
```
[ ! -e cloudflared ] && wget -O cloudflared https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64 && chmod +x cloudflared
```

<img width="1274" height="245" alt="image" src="https://github.com/user-attachments/assets/18e3866f-36ce-4e53-892e-c5bd340e8d8c" />


# 从 bashx.log 反推混淆过程
```
bash-obfuscate raw.sh -o obf1.sh
./bashfuscator -f obf1.sh -o obf2.sh --choose-mutators token/special_char_only command/reverse
bash-obfuscate obf2.sh -o obf3.sh
```

## 用到的工具
bash-obfuscate  
https://www.npmjs.com/package/bash-obfuscate  

bashfuscator  
https://github.com/Bashfuscator/Bashfuscator

安装方式见各项目自身README, 此处略.
