# Factorial solutions

// iterative function 
fac1(n) {
    if (n < 0) return NaN; 
    var acc = 1;
    for (var i = 1; i <= n; i++) {
        acc = acc * i;
    }
    return acc; 
}; 

//recursive function 
fac2(n) {
    if (n < 0) return NaN; 
    if (n === 1){ 
        return 1; 
    } 
    return n * factorial(n - 1); 
};

// one-liner for n >= 0 
function fac3(n) {return n < 2 ? 1 : n * fac3(n - 1); };

// with memoization
var cache = [1, 1]; 
var fac = function fac(n) { 
    if (n < 0) { return NaN; } 
    if (cache[n]) { return cache[n]; } 
    return cache[n] =  n * fac(n - 1); 
};

// invariant style function 
fac(n, acc) {
    acc = typeof acc === 'undefined' ? 1 : acc; 
    if (n == 1) { 
        return acc; 
    } 
    return fac(n - 1, n * acc); 
};
