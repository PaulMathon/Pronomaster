## COMPARE PASSWORDS

**Description : **Verify that two passwords are identical by using bcrypt.compare method.  
> **Params : **  
>passwordSent | string | password we want to compare  
>passwordStored | string | valid password  
>**Return : ** | Promise<Boolean> | return asynchronously a boolean set to true if the two passwords are identical.

```
const comparePasswords = async (passwordSent, passwordStored) => {
  const areEqual = await new Promise((resolve, reject) => {
    bcrypt.compare(passwordSent, passwordStored, (err, result) => {
      if (err) reject(err);
      resolve(result);
    });
  });

  return areEqual;
};
```