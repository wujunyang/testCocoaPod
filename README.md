# testCocoaPod
测试提交到官网Pod

1：创建podspec文件

pod spec create wjyTestCocoaPod

2：命令进行验证

pod lib lint wjyTestCocoaPod.podspec

3：注册CocoaPods账号，邮件验证

pod trunk register wujunyang@126.com 'wujunyang' --description='测试提交'

4：检查账号是否创建成功

pod trunk me

5：检测文件格式的有效性

pod spec lint --allow-warnings

6：提交上传

pod trunk push wjyTestCocoaPod.podspec --allow-warnings

7：验证是否上传成功

pod search wjyTestCocoaPod


注意：release版本不能带v. 直接如：0.0.1 否则会报，查找不到版本：

[iOS] unknown: Encountered an unknown error ([!] /usr/bin/git clone https://github.com/wujunyang/testCocoaPod.git /var/folders/qw/nrvzl2sj2l98qgpyqq6b3qvh0000gn/T/d20161101-11140-19txqzy --template= --single-branch --depth 1 --branch 0.0.1

注意：命名最好是有代表性，避免跟别人一样，否则会导致上传失败


成功后显示如下：

-> wjyTestCocoaPod (0.0.1)
   A short description of wjyTestCocoaPod.
   pod 'wjyTestCocoaPod', '~> 0.0.1'
   - Homepage: https://github.com/wujunyang/testCocoaPod
   - Source:   https://github.com/wujunyang/testCocoaPod.git
   - Versions: 0.0.1 [master repo]


注意：审核会后，当我pod search 自己库名的时候，这个时候始终没有出现。其实这个时候你需要重新配置下你本地的pod库索引 pod setup,等待同步、合并的过程，完成后再来pod search 'wjyTestCocoaPod'就出来了