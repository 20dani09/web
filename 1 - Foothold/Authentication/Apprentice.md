____

# Username enumeration via different responses

![[Pasted image 20240819055145.png]]

# 2FA simple bypass

```
Just try to access the next endpoint directly 

/my-account?id=carlos
```

# Password reset broken logic

```
Change username in POST request after password-reset link
```

![[Pasted image 20240819060645.png]]

# Username enumeration via subtly different responses

Grep extract

![[Pasted image 20240819074802.png]]

# Username enumeration via response timing

![[Pasted image 20240820125651.png]]

![[Pasted image 20240820125617.png]]

# Broken brute-force protection, IP block

You can reset the counter for the number of failed login attempts by logging in to your own account before this limit is reached. For example create a combined list with your valid credentials and with victim's creds

```
wiener - peter
carlos - kek
carlos - kek2
wiener - peter
carlos - kek3 etc...
```

![[Pasted image 20240821042000.png]]

# Username enumeration via account lock

It blocks only existing accounts, so try to brute the same list of passwords until one of accounts from the list is not blocked.
To brute password use grep with errors to find a request without error

![[Pasted image 20240821043248.png]]

![[Pasted image 20240821043325.png]]

# 2FA broken logic



