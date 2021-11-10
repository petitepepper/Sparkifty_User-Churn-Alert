# Sparkify_User-Churn-Alert



```
User Information
 |-- firstName: 	string		（×）
 |-- lastName: 		string  	（×）
 |-- gender: 		string 
 |-- location: 		string 
 |-- userAgent: 	string 		device info
 
User Count Information
 |-- userId: 		string 
 |-- level: 		string 		paid/free version
 |-- registration: 	long		registration timestamp

User Activities
 |-- artist: 		string 		（×）
 |-- song: 			string		（×）
 |-- auth: 			string		authentification status  
 |-- sessionId:		long 		
 |-- itemInSession: long 
 |-- ts: 			long		activity timestamp
 |-- status: 		long 		（×）service request status
 |-- method: 		string		（×）POST or GET
 |-- length: 		double 		use time 
```



> 思路：
>
> 1. 用户个人信息：年龄、设备？、（地区 -> 平均收入）
> 2. 用户使用情况：
>    - 平均使用时长
>    - 统计期间使用时长 - 注册开始月份使用时长
>    - 统计期间items数量 - 注册开始月份item数量
>    - 使用时长变化： -1（下降），0（不变），1（上升）
>    - items变化： -1（下降），0（不变），1（上升）
>    - 负面感受数量（thumb down）
>    - 正面感受数量（thumb up）
>    - 错误数量（error）
>    - 社交次数（add friend）
> 3. 用户账户情况：
>    - 账户存在时长
>    - 开始时的level
>    - 统计期间level变化：-1（下降），0（不变），1（上升）
>    - 
> 4. 预测结果 ： Churn
