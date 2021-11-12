# Sparkify_User-Churn-Alert



```tex
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





```tex
PAGE INFORMATION
+--------------------+------+------+
|                page|status| count|
+--------------------+------+------+
|           Downgrade|   200|  2055|
|       Save Settings|   307|   310|
|                Help|   200|  1454|
|Cancellation Conf...|   200|    52|
|            Settings|   200|  1514|
|          Add Friend|   307|  4277|
|             Upgrade|   200|   499|
|         Roll Advert|   200|  3933|
|      Submit Upgrade|   307|   159|
|               Error|   404|   252|
|                Home|   200| 10082|
|               About|   200|   495|
|     Add to Playlist|   200|  6526|
|              Logout|   307|  3226|
|         Thumbs Down|   307|  2546|
|              Cancel|   307|    52|
|           Thumbs Up|   307| 12551|
|            NextSong|   200|228108|
|    Submit Downgrade|   307|    63|
+--------------------+------+------+
```



1. User's personal information:

   - gender

2. User account status:

   - Tenure (number of days since registration)

   - Number of active days

   - Level: `1` for `paid`, `0` for `free`

   - Change of service
     - Upgrade(page:`Submit Upgrade`): `1` for yes, `0` for no
     - Downgrade(page:`Submit Downgrade`): `1` for yes, `0` for no

3. Usage information:

   - Average length of use during the current window period

   - Change in average usage duration

   - Change in average items number 

   - Change in the number of pages visited :
     - negative feelings (`Thumbs Down`)
     - positive feelings (`Thumbs Up`)
     - errors (`Error`)
     - socialization (`Add Friend`)
     - advert (`Roll Advert`)
     - add to play list (`Add to Playlist`)
   - Number of pages visited in resent period 

> The "change" above is compared to the previous window period 

