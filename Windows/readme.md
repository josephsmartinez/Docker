# Windows Containers: Docker Is No Longer Just Linux

So you've maybe heard about "Windows Containers". Something that wasn't even possible till mid-2016 in Windows 10 Pro/Ent and not feasible in production with Docker Swarm until April 2017 with a Windows Server 2016 hotfix. They are awesome, but new!

To be clear, this course so far, even on Windows, is running what we've known as "Docker" for 4 years, which are now called "Linux Containers".

Today Docker is much more than Linux. When you think of images, which are kernel specific, we're now talking about Linux x64, Linux x86 (32-bit), Windows 64bit, and a bunch more. This course still largely focuses on Linux x64 images because 90% of the concepts are the same, but "Windows Containers" are the new hotness! Technically, they are Native Windows .exe binaries running in Docker containers on a Windows kernel, and have no Linux installed.

If you check the course Description, I mention at bottom in "Course Launch Notes" about Windows Containers as a future Section I plan to add.  When making this course in 2017, I didn't know anyone really using them because Swarm Overlay networking didn't work on Windows, Secrets didn't work yet, and there were lots of rough edges that people wouldn't find very useful.

But with the release of 17.09 stable, the story for Windows Containers is much better and I plan on a new section for this. Until then, here's some recent getting started videos from Docker and Microsoft:

## Windows Containers and Docker 101

Windows and Linux Parity with Docker

Windows Containers and Docker 101
https://www.youtube.com/watch?v=066-9yw8-7c
Windows and Linux Parity with Docker
https://www.youtube.com/watch?v=4ZY_4OeyJsw
Docker + Microsoft - Investing in the Future of your Applications
https://www.youtube.com/watch?v=QASAqcuuzgI
