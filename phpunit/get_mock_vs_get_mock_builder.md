# getMock vs. getMockBuilder

```
// long version
$myMock = $this->getMockBuilder(MyMock::class)->
    setMethods(['method1'])->
    setConstructorArgs(['arg1'])->
    getMock();

// "short" version
$myMock = $this->getMock(MyMock::class, ['method1'], ['arg1']);

// long version
$myMock = $this->getMockBuilder(MyMock::class)->
    disableOriginalConstructor()->
    setMethods(['method1'])->
    getMock();

// "short" version
$myMock = $this->getMock(MyMock::class, ['method1'], [], $mockClassName = '', $callOriginalConstructor = false);

// you can also do...
$myMock = $this->getMockForTrait(MyTrait::class);
$myMock = $this->getMockForAbstractClass(MyAbstract::class);
// or chain those on the end of getMockBuilder()
```
