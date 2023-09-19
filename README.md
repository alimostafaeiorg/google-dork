# google-dork

**site:**

Tells Google to show you results from a certain site only. This will help you quickly find the most reputable source on the topic that you are researching. For example, if you wanted to search for the syntax of Python’s print() function, you could limit your results to the official Python documentation with this search: print site:python.org.

**inurl:**

Searches for pages with a URL that match the search string. It’s a pow-erful way to search for vulnerable pages on a particular website. Let’s say you’ve read a blog post about how the existence of a page called /course/jumpto.php on a website could indicate that it’s vulnerable to remote code execution. You can check if the vulnerability exists on your target by searching inurl:"/course/jumpto.php" site:example.com.

**intitle**

Finds specific strings in a page’s title. This is useful because it allows you to find pages that contain a particular type of content. For example, file-listing pages on web servers often have index of in their titles. You can use this query to search for directory pages on a website:

intitle:"index of" site:example.com.

**link**

Searches for web pages that contain links to a specified URL. You can use this to find documentation about obscure technologies or vulner- abilities. For example, let’s say you’re researching the uncommon regu-lar expression denial-of-service (ReDoS) vulnerability. You’ll easily pull up its definition online but might have a hard time finding examples.The link operator can discover pages that reference the vulnerability’s Wikipedia page to locate discussions of the same topic: link:"https://en.wikipedia.org/wiki/ReDoS".

**filetype**

Searches for pages with a specific file extension. This is an incredible tool for hacking; hackers often use it to locate files on their target sites that might be sensitive, such as log and password files. For example, this query searches for log files, which often have the .log file extension, on

the target site: filetype:log site:example.com.

**Wildcard (*)**

You can use the wildcard operator (*) within searches to mean any char-acter or series of characters. For example, the following query will return any string that starts with how to hack and ends with using Google. It will64 Chapter 5 match with strings like how to hack websites using Google, how to hack appli-cations using Google, and so on: "how to hack * using Google"

**Quotes (" ")**

Adding quotation marks around your search terms forces an exact match.For example, this query will search for pages that contain the phrase how to hack: "how to hack". And this query will search for pages with the terms how, to, and hack, although not necessarily together: how to hack.

**Or (|)**

The or operator is denoted with the pipe character (|) and can be used to search for one search term or the other, or both at the same time.The pipe character must be surrounded by spaces. For example, this query will search for how to hack on either Reddit or Stack Overflow:"how to hack" site:(reddit.com | stackoverflow.com). And this query will search for web pages that mention either SQL Injection or SQLi: (SQL Injection | SQLi). SQLi is an acronym often used to refer to SQL injec-tion attacks, which we’ll talk about in Chapter 11.

**Minus (-)**

The minus operator (-) excludes certain search results. For example,

let’s say you’re interested in learning about websites that discuss hacking,

but not those that discuss hacking PHP. This query will search for pages

that contain how to hack websites but not php: `"how to hack websites" -php**.**`

You can use advanced search engine options in many more ways to

make your work more efficient. You can even search for the term Google

search operators to discover more. These operators can be more useful than

you’d expect. For example, look for all of a company’s subdomains by

searching as follows:

`site:*.example.com`

You can also look for special endpoints that can lead to vulnerabilities.

Kibana is a data visualization tool that displays server operation data such

as server logs, debug messages, and server status. A compromised Kibana

instance can allow attackers to collect extensive information about a site’s

operation. Many Kibana dashboards run under the path app/kibana, so this

query will reveal whether the target has a Kibana dashboard. You can then

try to access the dashboard to see if it’s unprotected:

`site:example.com inurl:app/kibana`

Google can find company resources hosted by a third party online,

such as Amazon S3 buckets (we’ll talk about these in more detail in “Third-

Party Hosting” on page 74):

`site:s3.amazonaws.com COMPANY_NAME`

Look for special extensions that could indicate a sensitive file. In addi-

tion to .log, which often indicates log files, search for .**php, cfm, asp, .jsp**, and

.**pl**, the extensions often used for script files:

`site:example.com ext:php`

`site:example.com ext:log`

Finally, you can also combine search terms for a more accurate search.

For example, this query searches the site example.com for text files that con-

tain password:

`site:example.com ext:txt password`

In addition to constructing your own queries, check out the Google

Hacking Database **(https://www.exploit-db.com/google-hacking-database/)**, a

website that hackers and security practitioners use to share Google search

queries for finding security-related information. It contains many search

queries that could be helpful to you during the recon process. For example,

you can find queries that look for files containing passwords, common

URLs of admin portals, or pages built using vulnerable software.

While you are performing recon using Google search, keep in mind

that if you’re sending a lot of search queries, Google will start requiring

CAPTCHA challenges for visitors from your network before they can per-

form more searches. This could be annoying to others on your network, so I

don’t recommend Google dorking on a corporate or shared networ
