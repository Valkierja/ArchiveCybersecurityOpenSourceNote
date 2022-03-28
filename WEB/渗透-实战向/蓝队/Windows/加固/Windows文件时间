来自:https://gist.github.com/pzxbc/813dbca68775beffa5011a3c221aac33

## 先创建文件new-item gh.txt

![](https://pic2.zhimg.com/80/v2-fd60fa7899b01b2112175ae8a7818961_hd.jpg)

## powershell显示文件的创建、最后修改、最后访问时间 属性

```
PS D:\godhat> (ls gh.txt).CreationTimeUtc
PS D:\godhat> (ls gh.txt).LastWriteTimeUtc
PS D:\godhat> (ls gh.txt).LastAccessTimeUtc
```

![](https://pic3.zhimg.com/80/v2-785fada2731541f55d8a29d75bc73c5e_hd.jpg)

## powershell设置文件的创建、最后修改、最后访问时间属性

```
PS D:\godhat> (ls gh.txt).LastAccessTimeUtc="2019-12-31 22:33:44"
PS D:\godhat> (ls gh.txt).LastAccessTimeUtc
```

![](https://pic2.zhimg.com/80/v2-3fc27427d2e3f958695fe38159b7877d_hd.jpg)

```
PS D:\godhat> (ls gh.txt).LastWriteTimeUtc="2019-12-31 11:22:33"
PS D:\godhat> (ls gh.txt).LastWriteTimeUtc
```

![](https://pic4.zhimg.com/80/v2-cf7e199bc9377122ad0b05493e63dc2b_hd.jpg)

```
PS D:\godhat> (ls gh.txt).CreationTimeUtc="1949-10-01 14:00:01"
PS D:\godhat> (ls gh.txt).CreationTimeUtc
```

![](https://pic3.zhimg.com/80/v2-b3bba8c11c9e2fe649ea6ca69b9776e6_hd.jpg)

## 目录/文件夹的时间属性修改，需要用到Get-ChildItem，如Fo1目录

```
$F=Get-ChildItem Fo1
$F[1].Name
$F[1].CreationTime
```