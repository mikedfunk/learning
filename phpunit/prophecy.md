# Prophecy in PHPUnit

Prophecy is much better than phpunit's mock builder IMHO. It matches the actual calls better since you specify method calls just like you would in the actual class. Example:

```php
<?php
    class MyClass
    {
        /** @var \Request */
        protected $request;
        
        public function __construct(Request $request)
        {
            $this->request = $request;
        }
        public function doSomething(): string
        {
            return $this->request->getParam('mything');
        }
    }

    class MyClassTest extends \PHPUnit\Framework\TestCase
    {
        /** @var \MyClass */
        protected $myClass;
        
        /** @var \Request */
        protected $request;

        public function setUp()
        {
            $this->request = $this->prophesize(Request::class);
            $this->myClass = new MyClass($this->request->reveal());
        }

        /** @test */
        public function it_does_something()
        {
            $this->request->getParam('myparam')->willReturn('mything');
            $this->assertEquals('mything', $myClass->doSomething());
        }
    }
```

You can also do similar to phpunit's `onConsecutiveCalls` with a callback, you can mock different methods with different inputs easily, you can do `willThrow(...)`, etc.
