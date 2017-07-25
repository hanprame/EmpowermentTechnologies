# Git Frequently Asked Questions

### I mistyped my remote URL when I ran `git remote add`. How do I fix it?

Let's say your real git remote URL is https://github.com/JohnerZulueta/hw2.git

But you instead typed `git remote add origin https://github.com/JohnerZulueta/hw2.gi` (you missed the last 't' in the URL)

Here's how to fix this:

Remove the remote ('rm' stands for 'remove')

```
git remote rm origin
```

Then add the correct URL:

```
git remote add origin https://github.com/JohnerZulueta/hw2.git
```

### I can't push to my account because another account is logged in

On the Windows Control Panel, go to User Accounts > Credential Mananger > Windows Credentials

Under Generic Credentials, remove everything for github.com

Try to push again and Windows will ask you to login with your github.com credentials
