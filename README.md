# instagramcrawler
A crawler for instagram.

A project for crawling [Instagram](https://wwww.instagram.com). The crawler logs in to the user account and fetches all the general information of 
**followers** // **following** like:
- Full Name
- Username
- Biography text
- Followers count
- Following count

The dump data is like:  

```json
{
    "full_name"     : "Full Name",
    "username"      : "username",
    "followers"     : [ user1_data, user2_data, ...],
    "following"     : [ user1_data, user2_data, ...]
}
```

Since **Instagram** is fully dynamic and its api is sandboxed(limited), [Selenium](http://selenium-python.readthedocs.io/index.html) is used to automate
the login, click on the followers/following link and extract all the usernames.

Finally, [Scrapy](http://doc.scrapy.org/en/latest/index.html) is used to crawl all the relevant data for the usernames collected.

--------------------------------

## Dependencies
It uses python3 along with scrapy and selenium, firefox driver

``bash
wget https://github-production-release-asset-2e65be.s3.amazonaws.com/25354393/2bee491a-9ad6-11e7-8837-713392ec83cf?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH53A%2F20170921%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20170921T030703Z&X-Amz-Expires=300&X-Amz-Signature=b6c45abb3029f382251b85991d2b9ea69395cb36ac302f5709bd25110363485a&X-Amz-SignedHeaders=host&actor_id=8553294&response-content-disposition=attachment%3B%20filename%3Dgeckodriver-v0.19.0-linux64.tar.gz&response-content-type=application%2Foctet-stream
```

```bash
pip install scrapy
```

```bash
pip install selenium
```

## Usage
Run scrapy spider as:

```bash
scrapy crawl instaspider
```


Also, the crawler `instaspider.py` requires a path to json file. The **JSON** format is:

```json
{
    "USERNAME"  :   "your_user_name",
    "PASSWORD"  :   "your password"
}
```




