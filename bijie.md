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