# mybatisplus-jpa-converting
mybatisplus &amp; jpa converting

一般来说, 技术总是从基础的往高级的迭代, 从难用的往好用的迭代; 

但是如果你们的管理层是一堆傻逼, 要从 mybatis-plus 迭代成 jpa; 

那么本文提供了一种快速转化 mybatis-plus 到 jpa 的思路. 

1. 使用 jdbc-template 实现复杂语句
> ! 千万不要怕留下屎山, 如果你们的公司决定从 mybatis-plus 迭代成 jpa, 那么说明这是一帮傻逼; 赶快留下一堆屎山代码然后离职吧 ! 

2. 使用正则批量替换 mapper 层
> 你不会还想一句一句改吧, 能访问github的你, 难道像你们公司管理层一样是个傻逼 ? 
reg: (BaseMapper<)+(\w+)(>)
replace: JpaRepository<$2,String>, JpaSpecificationExecutor<$2>
