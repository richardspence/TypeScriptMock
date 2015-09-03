# TypeScriptMock

This a thin wrapper around jasmine spies that allows 


Example usage:

export interface IBiz{
  helloWorld():string

}

export class Program{
private _biz:IBiz;
  constructor(biz:IBiz){
    
      this._biz = biz;
  }
  
  public printHelloWorld(){
    console.log(this._biz.helloWorld());
  }
}



var mock = new Mock<IBiz>();
mock.Setup(p=>p.helloWorld()).andReturns("Hey");

//use the mock
var p = new Program(p);
p.printHelloWorld();
