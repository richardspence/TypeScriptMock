# TypeScriptMock

This a thin wrapper around jasmine spies that allows 


Example usage:
```TypeScript
export interface IBiz{ 
	helloWorld():string
}

export class Program{ 
	private _biz:IBiz; 
	constructor(biz:IBiz){
  		this._biz = biz;
	}

	public printHelloWorld()
	{ 
		console.log(this._biz.helloWorld()); 
	}
 }




var mock = new Mock<IBiz>();
mock.setup(p=>p.helloWorld).andReturns("Hey");

//use the mock
var p = new Program(mock.getObject());
p.printHelloWorld();
```
