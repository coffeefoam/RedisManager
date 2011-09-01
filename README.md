实现RedisManager继承 org.apache.catalina.session.StandardManager， 
MemcachedSession继承 org.apache.catalina.session.StandardSession。 

安装步骤:
1. 复制:wjw-redismanager.jar,(已经把xstream,xpp3,redis,common-pool加入到内部引用)
到x:\apache-tomcat-6.X.XX\lib下面

2. x:\apache-tomcat-6.X.XX\conf下文件context.xml中添加:
    <!-- use redis keep session -->
    <Manager pathname="" className="org.apache.catalina.session.ext.RedisManager" 
             serverlist="${ip1}:${port1},${ip2}:${port2}" minConn="5" maxConn="100" socketTO="6000" debug="false"
    />
当需要验证时这样添加:		
    <!-- use redis keep session -->
    <Manager pathname="" className="org.apache.catalina.session.ext.RedisManager" 
             serverlist="${ip1}:${port1}:${password1},${ip2}:${port2}:${password2}" minConn="5" maxConn="100" socketTO="6000" debug="false"
    />
		