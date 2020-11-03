# Docker-Echo
The most useless docker container I could think of...

its echo. like the binary "echo". Yes that one the one where you go "echo hello" and it goes hello back. like seriously nothing special...

### Back Story!
I was looking for a project and someone mentioned that I should containerize a security tool that I might use. Well having a look at what I could do I noticed that everything had a docker image. Damn! no originality for me... I also noticed that there was a lot and i mean A LOT of things that really didn't need to be containerized. So that got me think... DOOM! I present you the most useless binary I could think for containerizing. Like there is no reason to containerize "echo" that I could think of.

### But Wait There's More...
I didn't want to just make the easiest Dockerfile and call it a day. Oh no no no. Lets make this good. so you've build the docker image. and you can run it like normal.
```bash
sudo docker run --rm -it alpine-echo "text here"
```

Lets make sure that people use this!
1. Disable the local machine echo!
```bash
mv $(which echo) $(which echo).bak
```
Sweet the local echo binary is now taken care of!
2. Create an Alias!
```bash
alias echo="sudo docker run --rm -it alpine-echo"
```
Now everytime the user in this session writes echo it will run the docker image with their args.
3. But wait, Why not for all users...
```bash
echo 'alias echo="sudo docker run --rm -it alpine-echo"' >> /etc/profile
echo 'alias echo="sudo docker run --rm -it alpine-echo"' >> /etc/bash.bashrc
```
Yeah, thats better!

## Final Enjoy, You can now tell everyone that you've containerised your workflow!!
