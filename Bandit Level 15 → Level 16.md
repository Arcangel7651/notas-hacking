## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**
## Datos de acceso al nivel
Usuario: bandit15
Contraseña: jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

## Solución
```bandit15@bandit:~$ nc localhost 30001
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 20 17:51:06 2024 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 20 17:51:06 2024 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 20 17:50:06 2024 GMT; NotAfter: Feb 20 17:51:06 2024 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEIivS1jANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjQwMjIwMTc1MDA2WhcNMjQwMjIwMTc1MTA2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQC4
XC9dgne8ha9I/vXn4uTtObLhI/PPyLyl4jyDQPp61VtsEMcOb95KhXxdtQiDtzSD
3KXQVFLaPlVGKDWSR9nV+GoazSNPmNLH/IMVrUYxXjYikPxo1jjYKyuqfjV5bNm3
Hz6z4eDl7wNbPRaPAMPo0WU23m9M04bKQHLINfN7Abz3a+7ChLeICrWXiXp9mWfj
PY8cK7Vayz0eHU4Lg64q4jUaXQqZ/ta1RqZEwv7ZuTKctcazpK/u2+h4zvQCPyLh
uDjUXZTLlIuhfjyKUJLQsmYHAQprV6sY3ybFN32dW6MSE0/ApT6Th0LzKeaYxk5b
3NIeaYyPeKsjqFSwy+2zAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQBQ
RXG1k+cB357X43fsiyaCQQh4RbWHOcg1jBes5eiC/H8MyC3ec1znXvOUfqJcWNQJ
9UJDMwbkpo+IcwJiOe9n/D3Zeypv1g+ta8KKLsQ+zcbp5RdltKy7GuO/s5WjVofE
/IHz/5g+IMoqqYLlquQ539CZykPMC9TB9uWfJj/i8faCox4gjtkSCri+27tUZuHi
eYR3zxY1ptsJti/pMaItC6Oc2/pSlotQ4fXdciLZYGXqlmSFBt8Y8/v1YkhME5gN
3HmBV/Zg1SghA57zYsbf3npvQwudr04f2iF493pe0VRN6DfiXTxWkJe1VKuyGHEr
Q4L4OdVlgMSeyYyKgFc7
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: D62C47970FEA81A412649371A97B1E89080BBF18A1D813552ACB5AA940AA2497
    Session-ID-ctx:
    Resumption PSK: 0CE3442E3916F37AFD0315B6040D1BB11DF322CD4CBD5D298B80E7FE94398E2021174342363C6EF6A456E6C3DE764618
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 81 c9 7a 81 90 61 a2 44-6e 83 ab 39 4b a2 9f d6   ..z..a.Dn..9K...
    0010 - 45 0a ab 20 bb fe 77 49-10 ad 51 8c bd 4b e8 dd   E.. ..wI..Q..K..
    0020 - 6e 3e 60 78 fe 6e 94 d6-58 df bf 72 51 40 3b e8   n>`x.n..X..rQ@;.
    0030 - 56 64 ca 50 e8 d6 dc 6b-e1 ae c2 77 69 2d 54 be   Vd.P...k...wi-T.
    0040 - 50 98 a0 e2 b7 01 a4 f4-2c ff 30 66 f2 fa 4a 06   P.......,.0f..J.
    0050 - 9a a1 36 68 71 65 52 d8-66 45 d4 12 04 46 50 06   ..6hqeR.fE...FP.
    0060 - 21 6a 3e 75 92 89 d2 1d-61 1f e0 af b6 1c df 61   !j>u....a......a
    0070 - 6e ba 95 ac 30 29 4b b7-2e 62 13 11 3c 09 80 58   n...0)K..b..<..X
    0080 - 30 91 3b 96 b6 fa 9b f0-de 1c 50 20 e8 ad 47 3e   0.;.......P ..G>
    0090 - 0f 43 03 a2 f8 e4 9f d7-30 2f 45 5c 0b 05 9e 01   .C......0/E\....
    00a0 - 07 17 85 3a df da 25 ef-95 2a 94 37 fc 53 8e d9   ...:..%..*.7.S..
    00b0 - 62 80 60 31 5c 7e 3b 76-f6 7e 23 20 c7 85 1d e4   b.`1\~;v.~# ....
    00c0 - d9 30 ac 32 a8 6d 94 cc-d6 7b 37 13 bd 74 ea 71   .0.2.m...{7..t.q

    Start Time: 1708457316
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 3E7D55D785A65E3471F13AB5F6B760B9AC5CD1CF6B5309BBF696D7CBAE743973
    Session-ID-ctx:
    Resumption PSK: CE88CBD4ADCBD72F7EB29C7EEA6029A0F080B7DAA472D944036D9F38485F4ED7D1F5061ADEE05AAAA61A54E7DE9109DD
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 81 c9 7a 81 90 61 a2 44-6e 83 ab 39 4b a2 9f d6   ..z..a.Dn..9K...
    0010 - 70 77 2f 75 d6 25 99 10-9b e1 54 73 a5 f3 21 a7   pw/u.%....Ts..!.
    0020 - 8c a2 24 36 9a 36 0a cf-60 ff a3 24 ac 5d 0a 2e   ..$6.6..`..$.]..
    0030 - 3e 86 84 ee ac 6b 3b 4f-ed 34 f9 c8 45 3b 9c 44   >....k;O.4..E;.D
    0040 - 77 39 c8 7b ef 33 b6 5b-05 ba 3a a5 ba 07 90 a3   w9.{.3.[..:.....
    0050 - a4 23 59 ab 20 75 c2 c9-3c 74 79 43 3e 09 9b cc   .#Y. u..<tyC>...
    0060 - 10 eb 4a 26 c5 81 c1 ef-4c 51 ce bb e0 3e 10 61   ..J&....LQ...>.a
    0070 - 56 59 0d 67 cc fb 1f 50-12 2e c0 a6 dd f4 4b bd   VY.g...P......K.
    0080 - e8 90 85 07 b3 2d 58 d7-43 05 eb 32 54 88 eb 3b   .....-X.C..2T..;
    0090 - 56 58 ef 42 a0 bd 6c 44-dc 09 01 a6 c1 f3 f3 57   VX.B..lD.......W
    00a0 - 22 e5 d1 d4 87 45 5d 28-a4 95 f8 09 0c 87 3f 22   "....E](......?"
    00b0 - e3 a7 13 6c b7 70 13 35-dd b0 91 37 bb e9 56 61   ...l.p.5...7..Va
    00c0 - 1e f2 2b 02 80 4f 70 d9-30 4b c8 84 23 2d 49 7a   ..+..Op.0K..#-Iz

    Start Time: 1708457317
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
```
## Notas Adicionales
## Referencias
