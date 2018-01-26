//Canvas helper variables
var pixelsBetweenNumbers = 30;
var pixelsBetweenArrays = 40;
var arrayNumberOnCanvas = 0;
var yOffset = -10;
var xOffset = 0;

var displayArray = function(array) {
    textFont(createFont("monospace"), 12);
    fill(0, 0, 0);
    
    arrayNumberOnCanvas++;
    for (var i = 0; i < array.length; i++)
    {
        var x = xOffset + (i+1)*pixelsBetweenNumbers;
        var y = yOffset +  arrayNumberOnCanvas * pixelsBetweenArrays;
        text(array[i], x, y);
    }
};
var drawSwapLine = function(firstPosIdx, SecondPosIdx){
    stroke(200, 100, 100);
    var x1 = xOffset + (firstPosIdx+1) * pixelsBetweenNumbers;
    var y1 = yOffset + (arrayNumberOnCanvas-1) * pixelsBetweenArrays;
    var x2 = xOffset + (SecondPosIdx+1) * pixelsBetweenNumbers;
    var y2 = yOffset + (arrayNumberOnCanvas) * pixelsBetweenArrays;
    // Center lines & prevent lines from intersecting characters
    x1 += 5;
    y1 += 2;
    y2 -= 12;
    x2 += 5;
    
    line(x1, y1, x2, y2);
};

var swap = function(array, firstIndex, secondIndex) {
    var temp = array[firstIndex];
    array[firstIndex] = array[secondIndex];
    array[secondIndex] = temp;
};

var indexOfMinimum = function(array, startIndex) {
    var minValue = array[startIndex];
    var minIndex = startIndex;
    for(var i = minIndex + 1; i < array.length; i++) {
        if(array[i] < minValue) {
            minIndex = i;
            minValue = array[i];
        }
    } 
    return minIndex;
};
var selectionSort = function(array) {
    // Reset array counter and display unsorted array.
    arrayNumberOnCanvas = 0;
    displayArray(array);
    for(var i = 0; i < array.length; i++){
        var minIndex = indexOfMinimum(array, i);
        swap(array, i, minIndex);
        displayArray(array);
        drawSwapLine(minIndex, i);
    }
};

// Draw a quadrant
stroke(0, 0, 0);
line(200, 0, 200, 400);
line(0, 200, 400, 200);

var array = [4, 3, 2, 1];
array = selectionSort(array);

xOffset = 200;
var array2 = [17, 21, 1, 19];
array2 = selectionSort(array2);

xOffset = 0;
yOffset = 190;
var array3 = [55, 11, 31, 29];
array3 = selectionSort(array3);

xOffset = 200;
yOffset = 190;
var array4 = [77, 85, 13, 11];
array4 = selectionSort(array4);
