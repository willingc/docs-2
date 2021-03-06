---
layout: api-command
language: Java
permalink: api/java/polygon_sub/
command: polygonSub
related_commands:
    polygon: polygon/
---

# Command syntax #

{% apibody %}
polygon1.polygonSub(polygon2) &rarr; polygon
{% endapibody %}

# Description #

Use `polygon2` to "punch out" a hole in `polygon1`. `polygon2` must be completely contained within `polygon1` and must have no holes itself (it must not be the output of `polygonSub` itself).


__Example:__ Define a polygon with a hole punched in it.

```java
import com.rethinkdb.gen.ast.Polygon;

Polygon outerPolygon = r.polygon(
    [-122.4,37.7],
    [-122.4,37.3],
    [-121.8,37.3],
    [-121.8,37.7]
);
Polygon innerPolygon = r.polygon(
    [-122.3,37.4],
    [-122.3,37.6],
    [-122.0,37.6],
    [-122.0,37.4]
);
outerPolygon.polygonSub(inner_polygon).run(conn);
```
