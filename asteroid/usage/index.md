Asteroids are simple websites or personal wikis that can interact with the Realms on the [GNO blockchain](https://github.com/gnolang/gno). 

You can use it to setup personal blogs, organisation websites, presenting newly discovered gems in the gnoland or just as experimental playgrounds. Imagine a wiki structure using markdown that can also render smart contracts (realms) from the https://gno.land blockchain, with redactional and stylistic autonomy.

# Minimal example

* **Compile** using `go build -o gnAsteroid` (or `make`)
* **Run** with `./gnAsteroid -asteroid-dir=example`, 
* **Visit** with a browser.

# To create a GNO asteroid

1. install gnAsteroid: `git clone https://github.com/gno/gnAsteroid`
2. Create an asteroid, let's say we're bob:

```
mkdir -p ~/asteroids/bob/
cd ~/asteroids
echo "Hello the Gnosmos! This is [Bob](about)'s blog :)" > bob/index.md
echo "I'm Bob from Neptune. In a previous life I was a sumo." > bob/about.md
```

That's it, we've created an asteroid with 2 pages.

Launch essentially like before:
```bash
gnAsteroid \
    -bind 127.0.0.1:8888 \
    -asteroid-name "Bob's asteroid" \
    -asteroid-dir ~/asteroids/bob
```
Test by visiting [http://127.0.0.1:8888](http://127.0.0.1:8888).

# How to link a realm

Just have a link like this in one of your markdown page: `[/r/demo/boards](/r/demo/boards)` and it will render the realm directly on your asteroid when you click the link; while still using gno.land of course.

# Styling an asteroid

Asteroids are very rough rocks.

In the context of asteroids, we call **style** a set 
of 3 folders: `css`, `font` and `img`. You may fork and
modify the style at [grepsuzette/gnAsteroid.style-gnosmos](https://github.com/grepsuzette/gnAsteroid.style-gnosmos).

Then `gnAsteroid -style-dir=/path/to/your/style -asteroid-dir=example`

When no style is specified, a default style embedded within `gnAsteroid` is used.

# TODO

- [ ] publish realm to register asteroid belts
- [ ] query asteroid belts to show links
- [ ] some kind of publication system
- [ ] better `<table>` styling
- [ ] investigate: web browser + gnoweb don't re-load css correctly at the moment

# More 

More links may arrive soon, e.g.:

* gnAsteroid.style-gnosmos: a simple style you can use and modify.
* gnAsteroid.docker: a docker system to serve asteroids (especially on Akash)

