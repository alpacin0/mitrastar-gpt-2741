mitrastar-gpt-2741\
Mitrastar HGU GPT-2741GNAC \
OS: linux 2.6.36 with BusyBox\
![kernel](https://github.com/alpacin0/mitrastar-gpt-2741/assets/16215180/c79601fe-73f3-4586-98d5-1344c0a1d7a8)

Escalation:\
```sed -i 's/cmdsh/sh/g' /etc/passwd```

Backup cfg decryption key:\
```openssl aes-256-cbc -k dF4pEeZjRIlmiv7pWW3kgf5g0bqFfsVj -d -in romfile.cfg -out romfile_decrypted.cfg```

I used version openssl-1.0.2 (same on router) because it will throw error on newer openssl versions.

Disable Backup encryption option:
```
/userfs/bin/tcapi set WebCurSet_Entry EncryptFile off
/userfs/bin/tcapi commit WebCurSet_Entry
```

Now that should let you download and upload the romfile freely with no more encryption.
If the tcapi commit gives you a forbidden message. Just do:
echo authenticated > /tmp/Authentication

