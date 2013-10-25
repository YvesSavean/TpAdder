function adder(/*args*/){
  var tab = Array.prototype.slice.call(arguments);
  return function(v){
  var result=0;
  tab.forEach(function(fonct){result = result + fonct(v);});      
  return result;
  }
}

function mult(v){
  return function(e){
    return v*e;
  }
}

function sub(x){
	return function(y){
		return x-y;
	}
}


adder(mult(2), mult(4))(2);
