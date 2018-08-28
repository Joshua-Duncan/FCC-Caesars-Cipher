# FCC Caesars Cipher
```
function rot13(str) { // LBH QVQ VG!

  //65-90 are uppercase letters, ignore everything else
  //65 - 77 add 13
  //78 - 90 subtract 13

  var hexArray = [];
  var convertedArray = [];

  //Loop through the string, checking the hex value of each character
  //If it's less than 65 or greater than 90 (special characters), just push it to the array
  //If it's less than 78 (65 - 77) add 13
  //If it's greater than 77 (78 - 90) subtract 13
  for(var i = 0; i < str.length; i++){
    if(str.charCodeAt(i) < 65 || str.charCodeAt(i) > 90){
      hexArray.push(str.charCodeAt(i));
    }else if(str.charCodeAt(i) < 78){
      hexArray.push(str.charCodeAt(i) + 13);
    }else
    {
      hexArray.push(str.charCodeAt(i) - 13);
    }
  }

  for(var elem in hexArray){
    convertedArray.push(String.fromCharCode(hexArray[elem]));
  }

  var newString = convertedArray.join("");

  //console.log(convertedArray);
  return newString;
}
```