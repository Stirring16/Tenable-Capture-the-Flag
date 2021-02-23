> # Author: Stirring
> # Team: ζp33d_0∫_Ψ1m3
> # 5 days with Tenable CTF

![Final_logo_Tenable-Capture-the-Flag-option2A](https://user-images.githubusercontent.com/62060867/108809234-f9406780-75da-11eb-95b4-432123579a06.png)



# 1. Tenable

# It's twice as hard

![photo_2021-02-23_16-57-43](https://user-images.githubusercontent.com/62060867/108828064-f5234280-75f8-11eb-93db-7ed8e62b32e9.jpg)

# [linux_scan.db](https://drive.google.com/file/d/1i2fg9jypW49S4wLoVzk8tksUdotk2aiL/view?usp=sharing)

Bài 25đ bỏ qua :v mình làm 100đ đi :D

Để làm được bài này bạn cần download tool [nessus](https://www.tenable.com/products/nessus) và đăng kí account

![151966161_436642427540778_3987250653273246281_n](https://user-images.githubusercontent.com/62060867/108829217-7b8c5400-75fa-11eb-80d2-badbda40964b.png)

Sau khi xem sơ lượt tất cả và tìm hiểu về nessus mình phát hiện được info Debugging Log Report 

![152039920_441401620397173_1841589633413859391_n](https://user-images.githubusercontent.com/62060867/108829224-7d561780-75fa-11eb-9571-78838d03635a.png)

Check tất cả các file ở 2 host ```172.26.48.52``` và ```172.26.48.53```.
Cả 2 host đều có 2 file ```get_flag.log```

2 file đều có lệnh ```cat /tmp/flag | xxd -p``` nhưng chỉ có file ở host ```172.26.48.53``` là có giá trị trả về

```2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e
2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e
2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e
2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e
2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e
2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e
2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e
2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e2e74
68652022636f6d6d616e642220666c61672069733a20666c61677b507230
6772346d6d316e67204d7535372038332037683320507230633335352030
662050757474316e67203768336d20316e7d0a
```
![151644268_765981977675452_5989870040192242832_n](https://user-images.githubusercontent.com/62060867/108829235-7fb87180-75fa-11eb-8b4c-590ee8afbf80.png)

Đây là một đoạn mã hex. Decode nó ngay :D

![152062177_413316239965239_6069501778380126998_n](https://user-images.githubusercontent.com/62060867/108829241-80e99e80-75fa-11eb-87eb-32ecd5f679f0.png)

So we got the flag: ```flag{Pr0gr4mm1ng Mu57 83 7h3 Pr0c355 0f Putt1ng 7h3m 1n}```


# 2. MISC 

# Esoteric

![152238828_279376753605895_3794260692782181089_n](https://user-images.githubusercontent.com/62060867/108809590-c6e33a00-75db-11eb-9fa9-ba48fd15dfa0.png)

```--[----->+<]>.++++++.-----------.++++++.[----->+<]>.----.---.+++[->+++<]>+.-------.++++++++++.++++++++++.++[->+++<]>.+++.[--->+<]>----.+++[->+++<]>++.++++++++.+++++.--------.-[--->+<]>--.+[->+++<]>+.++++++++.>--[-->+++<]>```

Bài này đối với những ai chơi CTF nhiều thì nhìn vào là biết ngay là [BrainFuck Language](https://en.wikipedia.org/wiki/Brainfuck) Decode thôi

![152061856_477361906616988_4274919946407715156_n](https://user-images.githubusercontent.com/62060867/108809874-5ab50600-75dc-11eb-93e0-154985d76ae3.png)

So we got the flag: ```flag{wtf_is_brainfuck}```

# Reggie McRegex 

![download (1)](https://user-images.githubusercontent.com/62060867/108810393-9c927c00-75dd-11eb-824b-b035ca53537b.png)

[Haystack.txt](https://drive.google.com/file/d/17wwcRsnkcy1m2iX58KRLY40j6ImWwAVy/view?usp=sharing)

Bài này cho ta 1 file haystack.txt trong đó chứa hàng trăm ngàn flag giả và chỉ có 1 flag thật
Với dữ kiện đề cho: 
1. Flag có định dạng:  flag{this_is_a_flag}
2. Và The text maximum là 16 kí tự
Với [Regular expression](https://en.wikipedia.org/wiki/Regular_expression) ta có thể giải quyết một cách nhanh chóng

Ta có thể viết 1 script [Regex.py](https://drive.google.com/file/d/1Tp7Nz9zP2nXdmBf5lJqhPitGV_F7F11q/view?usp=sharing)

![download (4)](https://user-images.githubusercontent.com/62060867/108815428-0b280780-75e7-11eb-84d1-d8087e1dee50.png)


hoặc dùng tool [Regex101](https://regex101.com/) với Regex là ```flag{\w+_\w+_\w+}```

![151826332_485149099154310_7975783141815449899_n](https://user-images.githubusercontent.com/62060867/108812209-4d4e4a80-75e1-11eb-86d5-c917aef94e0e.png)

So we got the flag: ```flag{thy_flag_is_this}```


# Quit messing with my flags

![download (2)](https://user-images.githubusercontent.com/62060867/108812100-14ae7100-75e1-11eb-9212-1c80c9172c0b.png)

```flag{161EBD7D45089B3446EE4E0D86DBCF92}```

Nhìn vào trong giống MD5 :D thử ngay với [Crackstation](https://crackstation.net/)

So we got the flag: ```flag{P@ssw0rd}

# Broken QR

![152457562_822859224962127_2172475289763107061_n](https://user-images.githubusercontent.com/62060867/108814662-c6e83780-75e5-11eb-95bb-e0203a2221aa.png)

Dựa vào QRcode-Structure t nhận ra qrcode này bị xóa mất 1 số điểm 

![screenshoot](https://postech.vn/wp-content/uploads/2020/08/Cau-truc-cua-QR-Code.jpg)

Vì vậy mình đã dùng Pain để khôi phục lại một số điểm cho đến khi nó nhận 

![download (3)](https://user-images.githubusercontent.com/62060867/108814919-365e2700-75e6-11eb-97e0-6583dda59782.png)


# 3. Stego

# Easy stego

![download (5)](https://user-images.githubusercontent.com/62060867/108815828-aae59580-75e7-11eb-8651-266cfd878c79.png)

![EasyStego](https://user-images.githubusercontent.com/62060867/108815864-b769ee00-75e7-11eb-84f2-cead1300304a.png)

Ở bài này mình đã dùng [Stegosolve](https://github.com/eugenekolo/sec-tools/tree/master/stego/stegsolve/stegsolve) để giải quyết

Dùng lệnh: ``kali㉿kali)-[~/Desktop]
             └─$ java -jar stegsolve.jar``
để mở stego

![152755029_448145076505127_8564858863448144188_n](https://user-images.githubusercontent.com/62060867/108817504-9060eb80-75ea-11eb-8878-53628b7e0ee9.png)

Xem từng kênh màu để lấy flag

![download (6)](https://user-images.githubusercontent.com/62060867/108818125-84295e00-75eb-11eb-822e-5315b2766d25.png)

# Hackerman

![151328863_1948840848587567_5813606126418508407_n](https://user-images.githubusercontent.com/62060867/108818728-63153d00-75ec-11eb-8cdc-3307bfc5d508.png)

![151694676_939873353486862_8827553652452747363_n](https://user-images.githubusercontent.com/62060867/108818736-64df0080-75ec-11eb-9c44-b62d32d692e9.png)

Nhìn hacker có vẻ ngầu lòi, vì vậy mình đã mở HxD lên để xem có flag không :D

![151236969_2760628274192041_3820245684639661169_n](https://user-images.githubusercontent.com/62060867/108818743-67d9f100-75ec-11eb-885d-55359e3d815d.png)

# Numerological
![152867920_2514028242231841_3059700887937238711_n](https://user-images.githubusercontent.com/62060867/108819318-4a595700-75ed-11eb-8f32-90f90aae8e60.png)

![shield](https://user-images.githubusercontent.com/62060867/108819355-53e2bf00-75ed-11eb-803a-a5e587d78055.png)

Đầu tiên mình ```binwalk``` thử xem họ có giấu thông tin gì trong hình không

![153770785_190200839562859_6016746755781834055_n](https://user-images.githubusercontent.com/62060867/108819322-4af1ed80-75ed-11eb-8416-626f7206d8f8.png)

Sau khi ```binwalk``` mình phát hiện có 1 file ảnh bên trong vì vậy mình đã dùng lệnh ``` binwalk --dd=".*"``` và có được bức hình với các kí tự lạ

![7839D](https://user-images.githubusercontent.com/62060867/108819367-59d8a000-75ed-11eb-92f9-4f6d7484a2bd.png)

Sau khi search google tìm kiếm mình biết đoạn mã này là [The Ciphers ò the Monk](https://en.wikipedia.org/wiki/The_Ciphers_of_the_Monks)

![cistern](https://user-images.githubusercontent.com/62060867/108819549-8ee4f280-75ed-11eb-9047-5e7e2cb78d04.png)

Theo như nguyên tắc trên thì mình đã giải ra được một dãy số

```3637 3639 3734 3265 3639 3666 3266 3461 3734 3461 3631 3538```

Tưởng chừng đây là flag nhưng submit thử thì không phải, vì vậy mình đã đi decode

![153274169_171192534591960_6058492418380315128_n](https://user-images.githubusercontent.com/62060867/108820543-e9cb1980-75ee-11eb-9596-ec3c6adeb845.png)

Decode 2 lần Hex mình có được link ```git.io/JtJaX``` 

So we got flag: flag{th0s3_m0nk5_w3r3_cl3v3r}

# 4.Forensics 

# H4ck3R_m4n exp0sed! 1

[H4ck3R_m4n exp0sed.pcapng](https://drive.google.com/file/d/13QGrawptqmIGbXRtiFvZr4abZkAEpznx/view?usp=sharing)

Mở file ```pcapng``` bằng ```wireshark``` và xem các packet mình phát hiện có 1 file ```butter.jpg```
Sau đó mình ```Follow TCP stream``` và ở ```tcp.stream eq 10``` có file ở định dạng JIFI sau đó mình lưu lại dưới dạng ```raw``` với file ```flag.jpg```

![151266274_168300758437083_3600195824837985366_n](https://user-images.githubusercontent.com/62060867/108822222-5cd58f80-75f1-11eb-8453-ad7f0f7c0bce.png)

Và ta có flag đầu tiên

![flag](https://user-images.githubusercontent.com/62060867/108822683-ff8e0e00-75f1-11eb-8fac-93325671e2c0.jpg)

# H4ck3R_m4n exp0sed! 2

![153347325_4161305287248175_6760665231698818236_n](https://user-images.githubusercontent.com/62060867/108823231-bb4f3d80-75f2-11eb-8799-cba941d8a026.png)

Tiếp tục với file ở trên, tương tự ở ```Tcp.stream eq 6``` và ```tcp.stream eq 8``` ta có 1 file nén 7z và password

![152500695_769982780606138_4014549234300079868_n](https://user-images.githubusercontent.com/62060867/108823238-bc806a80-75f2-11eb-88fe-0fd075375fe3.png)

![152331210_923362361761920_688011380042963467_n](https://user-images.githubusercontent.com/62060867/108823244-bdb19780-75f2-11eb-985d-c78bb612c5d8.png)

![download (7)](https://user-images.githubusercontent.com/62060867/108823792-7d064e00-75f3-11eb-89c2-9cdb1c37c3db.png)

Dễ dàng ta có được flag thứ 2

# H4ck3R_m4n exp0sed! 3

![151263308_330699425025980_548407987706220556_n](https://user-images.githubusercontent.com/62060867/108826113-804f0900-75f6-11eb-8953-0c5c624c1f31.png)

Trong file .7z ta thấy còn một file ```dataz```

![152973317_882619672534696_1248014019608395850_n](https://user-images.githubusercontent.com/62060867/108826123-8218cc80-75f6-11eb-8c4a-5b4c91dc0320.png)

Remove space file ta thấy đây là mã hex. Decode thôi

![151164951_3849003558454212_6638031102582633550_n](https://user-images.githubusercontent.com/62060867/108826131-83e29000-75f6-11eb-9977-ea635de60e0a.png)

ohh Flag cuối cùng :D






























