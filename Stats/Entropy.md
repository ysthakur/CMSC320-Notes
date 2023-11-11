
Entropy is a measure of how much information something provides

- Measured in bits
- One bit of entropy is amount of information it takes to encode a yes/no signal

## Formula for Entropy

We need a function with the following properties:

- Continuous
- Should be 1 if all events are equally likely
- Should be 0 if outcome is certain
- Every time we double number of potential outcomes, entropy should increase by one

$\log_2$/$\lg$ satisfies these properties.

If all events are equal probability, then:

$$
H(x) = \lg\left(\frac 1 p\right)
$$

Otherwise:

$$
H(x) = -\sum_x p_x \cdot \lg\left(p_x\right) = \sum_x p_x \cdot \lg\left(\frac 1 {p_x}\right)
$$

(note the minus sign)