# Year 9 — Day 8

## What I Did
Today was actually huge.I **FINALLY finished the HTML course** and even cleared the **Computers Course** on freeCodeCamp too! Honestly feels so good to get those out the way. On top of that, I went back onto TryHackMe and 
managed to pull off a full attack on the Fowsniff machine. I spent a lot of time enumerating hashes and fighting with reverse shells, but I **finally got root**!

--

## Improvements
1. Built a Movie Review page using semantic tags like `<main>` and `<ul>` to list out all the cast members and the ratings
2. Made a Multimedia Player using `<audio>` and `<video>` tags—I even added a `<track>` for captions so it's actually accessible
3. **Password Enumeration:** Instead of just brute forcing everything, I found a Pastebin leak and manually cracked the hashes to find the right POP3 credentials
4. **Privilege Escalation:** Found a misconfigured script (`cube.sh`) that ran as root every time someone logged in, and I hijacked it to get my admin shell
5. **Shell Stability:** Learned that if `python` doesn't work on a target, always check for `python3` to get that reverse connection going

--

## Active Recall

**Q1: How did you get onto the system once you had the passwords from Pastebin?**  
A: I used the cracked passwords to log into the POP3 mail server. I read the emails (using `retr 1` and `retr 2`) which gave me the SSH password for the user `baksteen`.

--

**Q2: What was the "weak link" that allowed you to go from a normal user to root?**  
A: I found a file called `cube.sh` that belonged to the `users` group (which I was in). Because I had write access to it, and it was being run by a root process (the SSH banner/MOTD), I could put my own code in there.

--

**Q3: Why did the first reverse shell attempt fail on the target?**  
A: The script tried to call `python`, but the target machine only had `python3` installed. I had to update the command to use `python3` so it could actually run the socket code.

--

**Q4: What is the point of the `<track>` element in a video tag?**  
A: It's used to add subtitles or captions to a video. You have to give it a `src` for the actual file and set the `kind` (like subtitles) so people can read along with what's being said.

--

**Q5: In a reverse shell script, whose IP address do you actually have to put in?**  
A: You HAVE to use **your own IP** (the VPN one). Since it's a "reverse" shell, the target machine needs to know exactly where to send the connection back to.

--

## Reflection
Genuinely proud of today. I am actually so glad that I finally cleared the HTML and Computer courses. Getting root on Fowsniff was definitely the highlight. 
--

## Tomorrow
- Finally get started on the CSS basics on freeCodeCamp (selectors, colors, and all that)
- Write up that root exploit in my own words for my GitHub so I don't forget how I did it
- Get even more used to the Linux terminal now that I'm getting shells more consistently
