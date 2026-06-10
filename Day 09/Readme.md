# Day 9:  MariaDB Troubleshooting

**Subject:**

There is a critical issue going on with the `Nautilus` application in `Stratos DC`. The production support team identified that the application is unable to connect to the database. After digging into the issue, the team found that mariadb service is down on the database server.

Look into the issue and fix the same.

---

**Solution:**

- **journalctl**
    
    journalctl is a command-line utility used to query and display logs from the
    
    [**systemd-journald service](https://www.geeksforgeeks.org/linux-unix/journalctl-command-in-linux-with-examples/)** on Linux systems. It provides a centralized, high-performance way to manage binary-formatted logs from the kernel, services, and applications, enabling efficient troubleshooting through filtering by time, priority, or specific processes.
    
    [GeeksforGeeks](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAACfklEQVRYhe2WPWzTUBDH//fy4VRqaAKDE1ErJULsiAxISAi1ESyMqIwIqVUYkGBlohvMTK3aBRiBCcYoYmGrEBIzMuAGx1sUUgkn8I7Bfokd7HzAEIacFMV+fr+7e/fu/W26dv865mlirtEXCSwSWCTwPySQjBp0jP6ahKwCqASGDwVEXbdSn8c5nJWloBI6pW6OZeoFQNUY/yYznhWP0jtRgRlyf1Y2cfbiucFN9wS/DjvgNkA2gLw/kCfCle8rP4vZTvJNODg3ALoQDAigDTABlAmwzWwn+V5NCvUAQWx7INdJyo2CpeULVrpcsNLEYP8ZQKCavdobrMQLjjP+nc+my95PyyuWwXtFSzsIxRx9GTlGfy1un4cr9YKR6OWlTN0g0L6fyF7R0u7EsVF+Q1sAAMudRDvKgXp2nO1/BNEtAGCZcInoLrwtMgXEdhwfNz7zMdSbmYbXGwARX8Kw9J8mnZAoSwKAbbi7BKpNj5H6DzQsVVtGj6f28IvP69+0D/MTIuKTQIQQkZQb4zgpqKyaDuA6gApAOQAmSbk1gd0crbRK4BBADQAkictRQqPMNtzNYbL8yHOKGvxe8Hok2lqG+0Bdq3kCAITovww01j3n9I/1UdgpdXMjvWLqzUxDQDxWc1jQK9twI6tgG+6u6hkG7w0WoXTANtytYWkBgOvM9A7ERwAqBNz0Sw0AJoHWVddPZukqBqclzIaEyF7t7RDhYXQBBxZy8K9sSIiyncTb4xX5lMFLBDqF4TtAreq5SPRu61+XWqOex7MwmfEkiv1DioPmlLo5SC33NwKjWAi3rX9ZjlXXyO8BZT4YC0/HpsbOm/sX0SKBRQJzT+A3ixskP7zNHQkAAAAASUVORK5CYII=)
    
- Navigate into the db

![image.png](Day%209%20MariaDB%20Troubleshooting/image.png)

- check the issue

![image.png](Day%209%20MariaDB%20Troubleshooting/image%201.png)

if we can try to restart it

![image.png](Day%209%20MariaDB%20Troubleshooting/image%202.png)

we identify the issue : 

→ it’s a permission issue the mysql user can ‘t operate on the folder /var/lib/mysql like the folder is owned by root

![image.png](Day%209%20MariaDB%20Troubleshooting/image%203.png)

- attribute the ownership to mysql

![image.png](Day%209%20MariaDB%20Troubleshooting/image%204.png)

![image.png](Day%209%20MariaDB%20Troubleshooting/image%205.png)

- restart the server

![image.png](Day%209%20MariaDB%20Troubleshooting/image%206.png)

![image.png](Day%209%20MariaDB%20Troubleshooting/image%207.png)