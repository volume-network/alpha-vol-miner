## 注意

适配0.1.5版本的Vol主网节点，否则无法进行挖矿

## 使用方法

- 需要安装好Java JDK8，请自行安装好。

- 前提条件是矿工需要给矿池节点进行质押，质押量按照1T 300个VOL来计算，否则就不能产块。
比如你的矿工有500TB容量，那么你需要给矿池节点质押 500 * 300 = 150000个VOL，才能够产块。如果质押量不够，就不能产块了。

把 application.yml 和 miner-0.1.5.jar 这两个文件放在一起

然后，打开 application.yml，并作相应的修改：

- url：你的矿池节点的地址
- target_deadline: 建议值60000秒，太大的值没有意义，太小的值可能挖不到区块
- account_ids：你的矿工账户的id
- plot_dirs: plot文件目录，可以每行放一个

```
url: 'http://47.244.18.76:9125'
target_deadline: '60000'
account_ids:
  - '12346568111706357134'
plot_dirs:
  - 'D:\plotdata'
  - 'D:\plotdata1'
  - 'D:\plotdata2'
  - 'D:\plotdata3'
  - 'D:\plotdata4'
```
在Windows上面启动挖矿软件:
```
java -jar miner-0.1.5.jar
```

在Linux上面启动挖矿软件:
```
nohup java -jar miner-0.1.5.jar&
```

