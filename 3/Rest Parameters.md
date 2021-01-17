


var arr = [1,2,3,4]
var [first, ...rest] = arr
...rest 得在最後面



function add(...args){
    console.log(args)
    return args[0] +args[1]
}
console.log(add(1,2))