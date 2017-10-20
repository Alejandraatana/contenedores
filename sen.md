
# 

# Keybindings

Since I am heavy `vim` user, these keybindings are trying to stay close to vim.


## Global

```
/         search (provide empty query to disable searching)
n         next search occurrence
N         previous search occurrence
f4        display only lines matching provided query (provide empty query to clear filtering)
f5        open a tree view of all images (`docker images --tree` equivalent)
ctrl o    navigate to next buffer
ctrl i    navigate to previous buffer
x         remove buffer
q         remove buffer, quit if no buffer is left
ctrl l    redraw user interface
h, ?      show help
:         open command prompt
```

## Movement

```
gg, home  go to first item
G, end    go to last item
j         go one line down
k         go one line up
pg up
ctrl u    go 10 lines up
pg down
ctrl d    go 10 lines down
```

## Listing

```
@         refresh listing
f4        filtering, for more info run `help filter` in sen
```

## Image commands in listing

```
i         inspect image
d         remove image (irreversible!)
enter     display detailed info about image (when layer is focused)
```

## Container commands in listing

```
i         inspect container
l         display logs of container
f         follow logs of container
d         remove container (irreversible!)
t         stop container
s         start container
r         restart container
p         pause container
u         unpause container
b         open container's mapped ports in a web-browser
X         kill container
!         toggle realtime updates of the interface (this is useful when you are removing multiple
          objects and don't want the listing change during that so you accidentally remove something)
```

## Tree buffer

```
enter  display detailed info about image (opens image info buffer)
```

## Image info buffer

```
enter     display detailed info about image (when an image is focused)
i         inspect image or container, whatever is focused
```


## Container info buffer

```
enter     display detailed info about image (when image of the container is focued)
i         inspect image (when image of the container is focued)
```

