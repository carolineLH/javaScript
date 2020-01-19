# Null类型

null类型是第二个只有一个值的数据类型，这个特殊的值是null。

从逻辑角度来看，**null值表示一个空对象指针**，而这也正是使用typeof操作符检测null值会返回"object"的原因

undefined值是派生自null值的，所以：
```js
alert(null == undefined); //true
```

尽管null和undefined有这样的关系，但他们的用途完全不同。
无论在什么情况下都没有必要把一个变量的值显示的设置为undefined，可是同样的规则对null却不适用。
换句话说，只要意在保存对象的变量还没有真正的保存对象，就应该明确地让该变量保存null值。