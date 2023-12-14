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


Definition of Big O:

$T(n) \in O(f(n))$ if there are positive constants $c$ and $n_0$ such that $T(n) \leq cf(n)$ for all $n \geq n_0$

Consider two arbitrary functions of the form $g(n)=\log_{A}(n)$ and $f(n)=\log_{B}(n)$, where $A$ and $B$ are arbitrary constants. Through the logarthim change of base property, the function $g(n)$ can be rewritten as $g(n)=\frac{\log_{B}(n)}{\log_{B}(A)}$. Note that the denominator in this function is a constant, which if we say $k = \frac{1}{\log_{B}{A}}$ and substitute that in, we get the equation $g(n)=k\log_{B}(n)$


From the equations $g(n)=k\log_{B}(n)$, we can select a constant $c$ larger than $k$, such as $c = k + 1$ and any $n_0 \in 0 < \mathbb{R}$ and plug them into the definition of Big O. $k\log_{B}(n_0) \leq (k+1)\log_{B}(n_0)$. If you reduce this, you get the equation $ 0 \leq 1$, which is always true, and always meets the definition of Big O. Therefore, $\log_{A} n \in O(\log_{B} n)$. Since $A$ and $B$ are completely arbitrary constants, $O(\log_{A} n)$ and $O(\log_{B} n)$ are equivalent. Now, back to the original question, if we choose $A=5$ and $B=2$ or vice versa, we get that $O(\log_{5} n)$ and $O(\log_{2} n)$ are equivalent.


# References
Conferred with Clayton during the lab around when we went over this in class

Used this to find basic logarithm properties.
https://www.cuemath.com/algebra/properties-of-logarithms/