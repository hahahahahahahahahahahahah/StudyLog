## 2019/3/29

1. 全局设置git的账户密码，不用每次push都需要验证
2. git config --global credential.helper store

### selenium 模拟登录，并爬取登陆后的内容

1. 选择以无头模式打开网页 opt=webdriver.ChromeOptions(), opt.headless = true, driver = webdriver.Chrome(options=opt)
2. 模拟登陆，在登录页面找到账户密码对应的关键字位置，一般是用name查找
3. elem_user=driver.find_element_by_name('username')
4. elem_user.send_Keys('username')
5. elem_passwd=driver.find_element_by_name('password')
6. elem_passwd.send_keys('*********')
7. login_button=driver.find_element_by_name('submit')
8. login_button.click()
9. 有时候click()方法可能会不生效， 作为代替可以用键盘操作， from selenium.webdriver.common.keys import Keys
10. elem_passwd.send_Keys('Keys.RETURN')

## 2019/3/30

1. git clone https:
2. git fetch oringin dev  dev为远程分支名
3. git checkout -b dev(本地分支) origin/dev(远程分支)  创建本地分支并切换且关联远程分支
4. 如果创建时未关联远程分支，或需要修改关联， git branch --set-upstream-to=origin/dev(远程分支) dev(本地分支)
5. git pull origin dev(远程分支)  把远程分支拉取到当前分支  git pull oringin dev(远程):dev(本地) 把远程分支拉取到指定本地分支
6. git branch -vv 查看所有分支及关联状态

## 2019/3/31

1. tensorflow中 tensor的维度是 [batch,height,width,channels]
2. 一般分为构建阶段和执行阶段
3. 构建阶段一般是构建计算图中的各种operation, 一个计算图就是由各个operation和 流动的tensor构成的
4. 执行过程是由Session定义的, 数据则是存储在Variable内
5. 