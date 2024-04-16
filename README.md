# Code Style
a simple code style guide

欢迎关于风格改进建议和讨论 -> [issues](https://github.com/Sunrisepeak/codestyle/issues)

---

## C++ code style

> WIP | 临时版本

```cpp
#ifndef FILENAME_HPP_LIBNAME // 头文件宏规则风格 1
#define FILENAME_HPP_LIBNAME

#include <cpp.hpp> // *.hpp // 头文件后缀 2

/* 当前文件 直接使用的头文件 */

namespace codestyle { // 命名空间 全小写 (近可能左大括号在最后一个参数/标识同一行的末尾处) 3

class CppStyle { // 类名大驼峰 4
    
public:
    void my_func(long long param_long) { // 公有函数名/函数形参 小写 + _分隔 5
        param_long = 2 + param_long; // 运算符 之前 加空格 6
        intVal++;
    }

    int mIntVar; // 公有成员变量m*开始, 小驼峰 7

protected:
    double mDoubleVar_d; // 保护成员变量 *_d 8
    void my_func_d() {   // 

    }

private:
    char mCharVar_e;    // 私有成员变量 *_e
    void my_func_e() {  // 

    }
}; // CppStyle

class MyClass : public CppStyle {
public:
    MyClass() {
        // 继承的子类使用父类中成员时加上类作用域 9
        CppStyle::mIntVar = 0;
        CppStyle::mDoubleVar_d = 0.1;
        CppStyle::my_func_d();
    }
}; // MyClass

}; // codestyle 类与命名空间 结尾 注释

#endif

short gShortVar; // 全局变量 g* 大驼峰 10

int main() {
    codestyle::CppStyle *cppStylePtr { nullptr };
    cppStylePtr = new cppStylePtr();

    cppStylePtr->mIntVar = 1;
    cppStylePtr->my_func(2);

    delete cppStylePtr;
    return 0;
}
```

**全局风格**

- 函数名: 小写 + _ 分隔
- 变量: 驼峰式

**额外标识**

- 权限: 保护 *_d | 私有 *_e 
- 作用域: m*标识类成员变量 | 库内部尽可能使用作用域标识(例如9

> 原则上 **额外标识** 仅做库内部使用, 不体现在公有成员, 尽可能让库使用者无感使用

---

## Python code style

---

[linter]() | [google style](https://github.com/google/styleguide)
