---
title: "I want to understand the tweet GLSL"
---

from  [[Tweet GLSL]]

I need to understand this.
- [https://twitter.com/setchi/status/1251153387187367939](https://twitter.com/setchi/status/1251153387187367939)
glsl

```
void main(){vec2 p=(.5-fract(mat2(cos(-t*.4+vec4(1,33,11,1)))*(gl_FragCoord.xy*2.-r)/min(r.y,r.x)))*2.4;float q=length(p),a=atan(p.y,p.x)*2.5+t*2.;gl_FragColor=vec4(mix(q*.9*step(q,min(abs(sin(a))+.4,abs(cos(a))+1.1)*.7),.7,step(q,.15)));}
```

- ![image](https://gyazo.com/c886047f75a75510549a8c65963f2fe2/thumb/1000)

How it works.
- I heard there is a GLSL Sandbox.
- [Let's play with GLSL Sandbox | notargs.com](http://wordpress.notargs.com/blog/blog/2015/02/25/glsl-sandbox%e3%81%a7%e9%81%8a%e3%81%bc%e3%81%86/)
- How do I see error messages?
    - It was on the console.
- I changed t and r to time and resolution and it worked.
    - ![image](https://gyazo.com/a6858f7a158d6989efc49e5cabe03527/thumb/1000)

[OpenGL 4.x Reference Pages](https://www.khronos.org/registry/OpenGL-Refpages/gl4/html/indexflat.php)
- [step - OpenGL 4 Reference Pages](https://www.khronos.org/registry/OpenGL-Refpages/gl4/html/step.xhtml)
    - `step(edge, x) == x < edge ? 0.0 : 1.0`
- [fract - OpenGL 4 Reference Pages](https://www.khronos.org/registry/OpenGL-Refpages/gl4/html/fract.xhtml)
    - `x - floor(x)`
- [mix - OpenGL 4 Reference Pages](https://www.khronos.org/registry/OpenGL-Refpages/gl4/html/mix.xhtml)
    - `mix(x, y, a) == x * (1 - a) + y * a`

Scaling part by time
:

```
mat2(
    cos(-time * .4 + vec4(1,33,11,1))
) 
```


tiling
:

```
vec2 from_center_x2 = (gl_FragCoord.xy * 2. - resolution);
vec2 p1 = from_center_x2 / min(resolution.y, resolution.x); 
vec2 p2 = fract(p1); 
vec2 p=( .5 - p2 ) * 2.4;
```

- ![image](https://gyazo.com/ed45b38029f2e1c4b187beb7b7da4d4c/thumb/1000)

Distance from center
:

```
float q=length(p);
```


Angle from center
- Since it is multiplied by 2.5, 5 pi is the number of petals in one round, which is the number of petals. Since time is added, it rotates with the passage of time.
:

```
float a=atan(p.y, p.x) * 2.5 + time * 2.;
```


step(q, edge)
- 1.0 if the distance from the center is less than EDGE", so it can be used to paint around the center.

Outline shape
:

```
min(abs(sin(a))+.4, abs(cos(a))+1.1) 
```

- ![image](https://gyazo.com/87926436442193a2483cc6801bd1499d/thumb/1000)

Gradation according to distance from center
:

```
q * .9 * step( ... )
```


This is the center circle
:

```
step(q,.15)
```


What is the mix with fixed y
- Conditional branching: x when a is 0, y when a is 1, and so on

Code for scaling part
:

```
mat2 m = mat2(cos(-time * .4 + vec4(1,33,11,1)));
vec2 p2 = fract(m * p1);
```

- Magic numbers such as 33
    - It doesn't make sense to multiply by 2 pi since it's put in cos anyway.
    - A value close to a multiple of π/2 when calculated
    - It's just a technique for short coding.
    - Same code and behavior as below
:

```
float pi = 3.14159;
mat2 m2 = mat2(
  cos(-.4 * time + 1.), 
  cos(-.4 * time + pi * 0.5), 
  cos(-.4 * time + pi * 1.5),
  cos(-.4 * time + 1.));
vec2 p2 = fract(m2 * p1);
```

    - This is what happens when sin is also used
:

```
float t = -.4 * time;
mat2 m2 = mat2(cos(t + 1.), -sin(t), sin(t), cos(t + 1.));
vec2 p2 = fract(m2 * p1);
```

        - Without +1. for cos, it would be just a rotation.

I've made a few modifications based on what I've seen so far.
- ![image](https://gyazo.com/c42b981ccaaa5d56e2052158edb93102/thumb/1000)
- [http://glslsandbox.com/e#72257.0](http://glslsandbox.com/e#72257.0)

---
This page is auto-translated from [/nishio/つぶやきGLSL理解したい](https://scrapbox.io/nishio/つぶやきGLSL理解したい) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.