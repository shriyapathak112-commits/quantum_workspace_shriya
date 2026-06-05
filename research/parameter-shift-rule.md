# Parameter Shift Rule

To navigate the cost landscape accurately, optimizers require gradient evaluations. Because quantum hardware evaluates functions through measurement probabilities, analytical gradients are computed using the Parameter Shift Rule.

For a gate parameterized by an angle $$ $\theta_i$ $$, its exact derivative can be calculated without numerical finite-difference approximations by shifting the parameter by a fixed constant ($$ $\pm \frac{\pi}{2}$ $$):

$$
\frac{\partial \langle\hat{H}\rangle}{\partial \theta_i} = \frac{\langle\hat{H}\rangle_{\theta_i + \frac{\pi}{2}} - \langle\hat{H}\rangle_{\theta_i - \frac{\pi}{2}}}{2}
$$

This mathematical guarantee bypasses operational errors introduced by traditional numerical finite differences ($$ $\pm \epsilon$ $$) which are susceptible to hardware noise floor limitations.
