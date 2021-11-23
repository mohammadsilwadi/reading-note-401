# [reading-note-401](https://mohammadsilwadi.github.io/reading-note-401/)

## About Configuring Django Settings

### Managing Django Settings: Issues

- Different environments. Usually, you have several environments: local, dev, ci, qa, staging, production, etc. Each environment can have its own specific settings (for example: DEBUG = True, more verbose logging, additional apps, some mocked data, etc). You need an approach that allows you to keep all these Django setting configurations.

- Sensitive data. You have SECRET_KEY in each Django project. On top of this there can be DB passwords and tokens for third-party APIs like Amazon or Twitter. This data cannot be stored in VCS.

Sharing settings between team members. You need a general approach to eliminate human error when working with the settings. For example, a developer may add a third-party app or some API integration and fail to add specific settings. On large (or even mid-size) projects, this can cause real issues.

Django settings are a Python code. This is a curse and a blessing at the same time. It gives you a lot of flexibility, but can also be a problem – instead of key-value pairs, settings.py can have a very tricky logic.

Setting Configuration: Different Approaches
There is no built-in universal way to configure Django settings without hardcoding them. But books, open-source and work projects provide a lot of recommendations and approaches on how to do it best. Let’s take a brief look at the most popular ones to examine their weaknesses and strengths.
12 Factors
12 Factors is a collection of recommendations on how to build distributed web-apps that will be easy to deploy and scale in the Cloud. It was created by Heroku, a well-known Cloud hosting provider.

As the name suggests, the collection consists of twelve parts:

1) Codebase
2) Dependencies
3) Config
4) Backing services
5) Build, release, run
6) Processes
7) Port binding
8) Concurrency
9) Disposability
10) Dev/prod parity
11) Logs
12) Admin processes

- Each point describes a recommended way to implement a specific aspect of the project. Some of these points are covered by instruments like Django, Python, pip. Some are covered by design patterns or the infrastructure setup.

### django-environ

- Writing code using os.environ could be tricky sometimes and require additional effort to handle errors. It’s better to use django-environ instead.

## Setting Structure

- Instead of splitting settings by environments, you can split them by the source: Django, third- party apps (Celery, DRF, etc.), and your custom settings.
Naming Conventions
Naming of variables is one of the most complex parts of development. So is naming of settings. We can’t imply on Django or third-party applications, but we can follow these simple rules for our custom (project) settings:
Give meaningful names to your settings.


## SSH:
## What is SSH and why it is used?
SSH or Secure Shell is a network communication protocol that enables two computers to communicate (c.f http or hypertext transfer protocol, which is the protocol used to transfer hypertext such as web pages) and share data.


## How Does SSH Work
```
The SSH command consists of 3 distinct parts:

ssh {user}@{host}
```
When you hit enter, you will be prompted to enter the password for the requested account. When you type it in, nothing will appear on the screen, but your password is, in fact being transmitted. Once you’re done typing, hit enter once again. If your password is correct, you will be greeted with a remote terminal window.
### Symmetric Encryption
![](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/symmetric-encryption-ssh-tutorial.webp)


### Hashing
One-way hashing is another form of cryptography used in Secure Shell Connections. One-way-hash functions differ from the above two forms of encryption in the sense that they are never meant to be decrypted. They generate a unique value of a fixed length for each input that shows no clear trend which can exploited. This makes them practically impossible to reverse.
![](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/ssh-tutorial-hash.webp)
- Gaining an in-depth understanding of the underlying how SSH works can help users understand the security aspects of this technology. Most people consider this process to be extremely complex and un-understandable, but it is much simpler than most people think.