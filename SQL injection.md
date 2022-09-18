## SQL Injection
After solving "Network sniffing" and "Web server login" we login at netsec-forum.dk using the credentials 

```Username = carsten@netsec.aau.dk and Password = mormor1932```

Afterwards we are directed to an "internal forum" with a message board we can interact with. 


<img src="https://i.imgur.com/juNXHNd.png" width=50% height=50%>
After poking a bit around in the input field, we discover the message board is vulnerable to SQL injection

<img src="https://i.imgur.com/fgRnfqX.png" width=50% height=50%>

...hm no flag yet. 
Our next objective now seems to be finding the flag in the SQL database we now have access to.
We now try looking for valid tables using a "SELECT ... FROM ..." query.
Because the webserver output detailed error messages, we can do this with trial and error

<img src="https://user-images.githubusercontent.com/43621940/190901013-270ca32b-eb5e-4a44-85cd-0cb34e27cbdd.png" width=50% height=50%>

After a few tries we discover the table "users" and column "password".
In order to actually read the content visually, we use the concatenation operator `||` 
to concat the result from the SELECT query with the string being posted to the message board

... and voilá we got the flag

<img src="https://user-images.githubusercontent.com/43621940/190901502-7966fa6b-3f7c-47b4-b93f-9f13c741d4a1.png" width=50% height=50%>

