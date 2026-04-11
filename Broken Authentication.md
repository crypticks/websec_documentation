Websites may have an exposed admin panel.

## URL-based
Check /robots.txt for disallowed sites. If not fruitful, run a [[Dirbuster]] on the site.

Sometimes, the url is obfuscated. But some functionality based on that URL may be implemented directly in the src code of the site, and is visible to all users. ( Example: Javascript code that adds a link to the homepage if the user is an admin ). Something like:

```Javascript
var isAdmin = false;
if (isAdmin) {
   var topLinksTag = document.getElementsByClassName("top-links")[0];
   var adminPanelTag = document.createElement('a');
   adminPanelTag.setAttribute('href', '/admin-l2tutv'); // here's the url
   adminPanelTag.innerText = 'Admin panel';
   topLinksTag.append(adminPanelTag);
   var pTag = document.createElement('p');
   pTag.innerText = '|';
   topLinksTag.appendChild(pTag);
}
```


## Role storage
Parameters related to role of the user (admin=1, role=1, etc.) may be coded in cookies, URL, etc. (IDOR - Insecure Direct Object Reference)


## Brute forces
Websites relying solely on passwords
- Usernames can be validated on login pages that give info on incorrect attempts.

Check if HTTP responses contain useful usernames/ids.


## Bad 2FA
If 2FA is on a separate site from login, usually means you're already in a logged-in state. Maybe the website doesn't actually check the second page. Example: get account page URL from our own account, use correct username and pass on victim, and instead of going to second page from there, change URL to account page.