
## Exemple:

```python
# inputs x1, x2
x1 = Value(2.0, label = 'x1')
x2 = Value(0.0, label = 'x2')
#weights w1 & w2
w1 = Value(-3.0, label = 'w1')
w2 = Value(1.0, label = 'w2')

b = Value(6.7, label = 'b')

x1w1 = x1*w1; x1w1.label = 'x1w1'
x2w2 = x2 * w2; x2w2.label = "x2w2"
x1w1x2w2 = x1w1 + x2w2; x1w1x2w2.label = "x1*w + x2*w2"
n = x1w1x2w2 + b; n.label = 'n'
o = n.relu(); o.label = 'o'
#e = (2 * n).exp()
#o = (e - 1) / (e + 1)
#o.label = 'o'

o.backward()
draw_dot(o)
```
## Result:
![graph_grad](https://user-images.githubusercontent.com/65721811/217382502-35629691-3e07-432d-a6fb-e0b291588c8d.png)


