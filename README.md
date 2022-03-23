# domserver-docker-compose

This repo serves as running a managing a full domserver using `docker` and `docker-compose`

# How to run?

- Make sure, you have a working installation of `docker` and `docker-compose`
- For `judgehosts` to work correctly, you need to enable `cgroups` on host. More [here](https://www.domjudge.org/docs/manual/main/install-judgehost.html#linux-control-groups)
- Make a copy of `*.env.example` files to `*.env` file and edit environment variables to your needs

After you are sure, you have what it needs to run:

Run following in the repo directory on separate terminals:
> `docker-compose -f docker-compose-domjudge.yml up`
After this command you should have access to domjudge console at `http://localhost:8080/domjudge`
Login using `Admin` as username and get the password by running `docker exec -it domjudge_dj-server_1 cat /opt/domjudge/domserver/etc/initial_admin_password.secret`

Edit the `judgehost` user password after that and use that password in `judgehost.env` file

> `docker-compose -f docker-compose-judgehost.yml up`

That's it.

# Caution:

This is a quick and dirty way of running a domjudge server with judgehosts instance. 🤪
Use at your own risk...
