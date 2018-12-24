# --
多元数组转为扁平化数组的设计与实现

// Example
let givenArr = [[1, 2, 2], [3, 4, 5, 5], [6, 7, 8, 9, [11, 12, [12, 13, [14]]]], 10];
let outputArr = [1,2,2,3,4,5,5,6,7,8,9,11,12,12,13,14,10]

// 实现flatten方法使得
flatten(givenArr)——>outputArr


answer 1
function flatten(arr){
    var res = [];
    for(var i=0;i<arr.length;i++){
        if(Array.isArray(arr[i])){
            res = res.concat(flatten(arr[i]));
        }else{
            res.push(arr[i]);
        }
    }
    return res;
}

answer 2

function flatten(arr){
    return arr.reduce(function(prev,item){
        return prev.concat(Array.isArray(item)?flatten(item):item);
    },[]);
}

answer 3

function flatten(arr){
    while(arr.some(item=>Array.isArray(item)){
        arr = [].concat(...arr);
    }
    return arr;
}
