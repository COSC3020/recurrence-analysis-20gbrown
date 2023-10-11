[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=12094428&assignment_repo_type=AssignmentRepo)
# Recurrence Analysis -- Mystery Function

Analyze the running time of the following recursive procedure as a function of
$n$ and find a tight big $O$ bound on the runtime for the function. You may
assume that each operation takes unit time. You do not need to provide a formal
proof, but you should show your work: at a minimum, show the recurrence relation
you derive for the runtime of the code, and then how you solved the recurrence
relation.

```javascript
function mystery(n) {
    if(n <= 1)
        return;
    else {
        mystery(n / 3);
        var count = 0;
        mystery(n / 3);
        for(var i = 0; i < n*n; i++) {
            for(var j = 0; j < n; j++) {
                for(var k = 0; k < n*n; k++) {
                    count = count + 1;
                }
            }
        }
        mystery(n / 3);
    }
}
```

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

**Recurence Relation:**

$T(n)$ = $1$ if n $\leq$ 1 else $3T(\frac {n}{3}$) + n<sup>5</sup>

$T(n)$ = $3T(\frac {n}{3}$) + n<sup>5</sup>

=  $3$($3T$(($\frac {n}{3}$)} / 3) + ($\frac{n}{3}$)<sup>5</sup>) + n<sup>5</sup>

=  $9T$($\frac{n}{9}$) + $\frac{3(n^5)}{3^5}$ + n<sup>5</sup>

=  . . . 

($\frac{9}{9^5}$ + $\frac{3}{3^5}$ + 1) $n$

= 9($\frac{n}{9}$)<sup>5</sup>

$\frac{3^j}{(3^j)^5}$

for $i$ = $(log_3 n)$

= 3<sup>$log_3n$</sup> T($\frac{n}{3^{(\log_3 n)}}$) + $\sum_{log_3 n-1}^{j=0}$ $\frac{3^j}{(3^j)^5}$ + n<sup>5</sup>

= $\in$ $\theta$ $(n^5 (log_3 n))$


