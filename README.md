# Foamy-governor
peznaranja

![buh](https://github.com/nicolasbaez/Foamy-governor/blob/main/xp042.gif)
```javascript
setup = (_) => createCanvas((w = 500), w, WEBGL);
draw = (_) => {
  fill(0, 8, 16, 32);
  rect(-w, -w, w * 2, w * 2);
  rotateX(w);
  rotateY(w / 2);
  rotateZ(w / 4);
  for (i = 0; i < 2 * PI; i += 0.3)
    for (j = 0; j <= PI; j += 0.3) {
      n = noise(i, j, w);
      r = n * w * 0.6;
      stroke(255, n * w, 0);
      point(r * sin(i) * cos(j), r * sin(i) * sin(j), r * cos(i));
    }
  if (w == 500) saveGif("xp042.gif", 628, { delay: 0, units: "frames" });
  w -= 0.01;
};
