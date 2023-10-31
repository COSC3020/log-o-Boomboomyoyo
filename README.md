[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=12094573&assignment_repo_type=AssignmentRepo)
# Asymptotic Equivalences

In the lectures, we said that logarithms with different bases don't affect the
asymptotic complexity of an algorithm. Prove that $O(\log_{2} n)$ is the same as
$O(\log_{5} n)$. Use the mathematical definition of $O$ -- do a formal proof,
not just the intuition.

I have started with the formal definition of $O$ below. Add your answer to this
markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

$T(n) \in O(f(n)) \iff \exists c, n_0: T(n) \leq c \cdot f(n) \forall n \geq n_0$

# Response
First, a translation of Big O out of mathematical notation into words, so I can understand it more clearly.
A function $T(n)$ is an element of Big O of another function $f(n)$ if and only if there exists a value $c$ and $n_0$ where $T(n) \leq c(f(n))$ for all $n \geq n_0$.

Consider the functions $g(n)=\log_{2}(n)$ and $f(n)=\log_{5}(n)$. Through the logarthim change of base property, the function $g(n)$ can be rewritten as $g(n)=\frac{\log_{5}(n)}{\log_{5}(2)}$. Note that the denominator in this function is a constant. Then, consider the constants $c=10$ and $n_0=3$. Since $g(n) \leq c \cdot f(n)$ for all $n \geq n_0$, then $\log_{2}(n) \in O(\log_{5}(n))$. Therefore, $O(\log_{2} n)$ and $O(\log_{5} n)$ are equivalent.

Note that this holds for any two logarithmic functions of differing bases. 


# References
Conferred with Clayton during the lab around when we went over this in class

Used this to find basic logarithm properties.
https://www.cuemath.com/algebra/properties-of-logarithms/