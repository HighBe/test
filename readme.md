用于各种测试
```
for (初始化表达式;循环条件;迭代表达式) {              
    执行语句
}

{
    初始化表达式
    for (;循环条件;迭代表达式) {
        执行语句
    }
}

if (条件) {
    执行语句
}

```
```
contract C {
    function f() external pure returns (uint256 x) {
        assembly {
            mstore(0, 0x42)
        }
        assembly {
            x := mload(0)
        }
    }
}

contract C {
    event ev(uint[],uint);
    bytes s;
    constructor() {
        emit ev(new uint[](2),0);
        bytes memory m = new bytes(63);
        s = m;
    }
    function h() external returns (bytes memory) {
        s.push();
        return s;
    }
}
```
## 未定义行为
悬空引用
```
contract C {
    bytes x = "012345678901234567890123456789";
    function test() external returns(uint) {
        (x.push(), x.push()) = (0x01, 0x02);
        return x.length;
    }
}
```



