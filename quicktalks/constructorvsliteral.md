#Constructor Vs Literal notation 

When creating an object you may either build it in a literal or constructor way. The constructor notation looks like this:

  function myObj(){ 
  this.myProp1 = "abc";
  this.myProp2 = "xyz"; 
  }
  
The literal notation looks like this: 

  var myObj = {
   myProp1:"abc", 
  myProp2:"xyz", 
  }

In the majority of cases it is better to use literal notation, this is because it is neater, easier to read and shorter, especially if you are just using your array or object, as a simple storage container for data. Think KISS principles!

However in a few cases it may be more appropriate to use a constructor. This may be when you want to make some of your variables within the object private, if you want to add behaviour to your object,

  MyData.prototype.verify = function () { 
  return this.foo === this.bar;
   };
   
  
or if you need multiple instances of your object.

  var objLit = { 
  x: 0, 
  y: 0, 
  z: 0, 
  add: function () { 
  return this.x + this.y + this.z; 
  } 
  }; 

  var ObjCon = function(_x, _y, _z) { 
  var x = _x; // private 
  var y = _y; // private 
  this.z = _z; // public 
  this.add = function () { 
  return x + y + this.z; // note x, y doesn't need this. 
  }; 
  }; // use the objects: 
  objLit.x = 3; 
  objLit.y = 2; 
  objLit.z = 1; 
  console.log(objLit.add()); 

  var objConIntance = new ObjCon(5,4,3); // instantiate an objCon console.log(objConIntance.add()); 
  console.log((new ObjCon(7,8,9)).add()); // another instance of objCon console.log(objConIntance.add());



