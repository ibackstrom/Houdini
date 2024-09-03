
## My humble list of usefull VEX snippets


Ok, let's start with a classic xyz-primuv combo

```
// Get data from surface
xyzdist(1, @P, prim, uv);

// Set scattered point position
@P = primuv(2, "P", prim, uv);
```


![xyz](IMG/xyz.gif | width=100)


Another simple VEX lookat function

```
// points are looking to the second input 
// run over points 
@N = normalize(point(1, 'P', 0) - @P); @up = {0, 1, 0};
```

![lookat](IMG/Lookat.gif)


Pcopen is one of the most powerfull approach for VFX inside VEX. This is a simple dinsity measure snippet.

```
int pointCloud = pcopen(0, 'P', @P, ch('radius'), chi('max_points'));
int pcNumFound = pcnumfound(pointCloud);
f@density = fit(pcNumFound, 0, chi('max_points'), 0, 1);
```

![density](IMG/Density.gif)





