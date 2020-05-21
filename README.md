# NorthWatch Custom Domain
Setup a Custom Domain on NorthWatch with FREE SSL and Hosting!

## Setp 1
Fork this repository using the "Fork" button towards the top right-hand corner of the screen.

## Step 2
Go to the settings menu of your newly-forked version of this repository, and scroll down to the "GitHub Pages" section.  Select "master branch" for source.

## Step 3
In the "Custom Domain" text box, enter your domain name.

## Step 4
Create these DNS records on your website depending if you want to route NorthWatch to the root of your domain (xxx.com), or a subdomain (yyy.xxx.com).
### Root of Domain (xxx.com)
| Record Type | Value           | TTL (Time to Live) |
|-------------|-----------------|--------------------|
| A           | 185.199.108.153 | Auto               |
| A           | 185.199.109.153 | Auto               |
| A           | 185.199.110.153 | Auto               |
| A           | 185.199.111.153 | Auto               |
### Subdomain (yyy.xxx.com)
| Record Type | Value                | TTL (Time to Live) |
|-------------|----------------------|--------------------|
| CNAME       | [USERNAME].github.io | Auto               |

Be sure to replace [USERNAME] with your GitHub username.
## Step 5
You should be done!  All you need to do is go to the GitHub Pages section of your repository settings and wait for the SSL certificate to issue, and enable it!
