# 飞鸟v1.0框架 #

# 序言：#
	laravel太重？ Thinkphp无特色 ？ ci不够优雅？ 其他啥啥啥框架写出来无法维护 ？ 试试飞鸟框架，快速构建你的web项目。
# 特色 #
	轻量级，纯面向对象，可配置化，漂亮的调用库，基础工具健全，超美观的整体结构，模块化可自定义各类模块，安全可靠，项目持续维护，可超高效率开发web项目。
# 项目整体结构 #
  ![](http://47.106.95.82/webroot/images/项目整体结构.png )

# 核心类库文件 #
![](http://47.106.95.82/webroot/images/核心库文件.png)

# 配置文件 #
![](http://47.106.95.82/webroot/images/配置文件.png)

# 框架使用 #
	没错，所有操作如此简单。 app核心工厂，构建所有的基础库。 只有用到时才加载，而且它的依赖您这边都统统不用管。

	## 接收请求 ##
	$req = app('request')->all();

	## 返回视图响应 ##
	 return app('response')->view('welcome');

	## 配置文件的读取和写入 ##
		app('config')->set('aa','hah');
		app('config')->get('aa','hah');
		app('config')->delete('aa','hah');


	## 缓存 ##
		设置缓存：
 		app('Cache')->set('aa','haha',3600*24);
		获取缓存：
		app('Cache')->get('aa','haha',3600*24);

	## 文件 ##
		上传
		app('file')->upload('default');
		下载
		app('file')->download($fileName);
	
	## excel ##
		导入
		app('excel')->import('aa.txt');
		导出
		app('excel')->export($title=array(), $data=array(), $fileName='', $savePath='default', $isDown=true);
	
	## 表单验证 ##
		验证邮箱
		app('form')->checkEmail('aa');

	## 加密解密 ##
		$encrypt = app('encrypt')->encrypt('aa');
		$decrypt = app('encrypt')->decrypt('asdfsdfsdfsdfda');
	
	## web-token ##
	    $jwt = app('jwt')->issue(['user'=>'feiniao','user_id'=>1]);

	## 模拟请求 ##
		app('curl')->post($url, $data=[])；

	## 日志 ##
		app('log')->info('aa');

	## 数据库操作 -orm ##
		一个好的框架怎么会没有封装好的orm呢？ 此框架绝对够用。
		数据库操作。
		-获取某一条数据
     	$goodsModel = new GoodsModel();
        $rowobj = $goodsModel->first(['id=7']);
        $name =  $rowobj->goods_name;

# 后序 #
	是不是超级简单，超级爆炸。 赶紧试试吧！！


