---
description: 代码修改注释规范，适用于所有代码变更场景。当修改、删除或新增代码时，必须按照 wzy delete / wzy patch 注释规范进行标注。
alwaysApply: true
---

# 代码修改注释规范

## 规则说明

在修改**已有项目**的代码时，必须严格遵守以下注释规范，不得直接删除原有代码，不得省略标记注释。

**适用范围**：仅适用于对已有项目代码的修改。如果是从零开始的新建项目，不需要添加 `wzy delete` / `wzy patch` 注释，代码直接写干净即可。

---

## 一、删除代码规范（wzy delete）

**禁止直接删除原有代码**，必须用对应语言的注释将其注释掉，并在注释块的最前面和最末尾加入标记。

### 格式

```
// wzy delete start
// 原有代码（注释掉）
// wzy delete end
```

### 各语言示例

**Java / C / C++ / Kotlin / Go / Swift（单行注释 `//`）：**
```java
// wzy delete start
// oldMethod();
// int oldVar = 0;
// wzy delete end
```

**Python / Shell / Ruby（单行注释 `#`）：**
```python
# wzy delete start
# old_function()
# old_var = 0
# wzy delete end
```

**HTML / XML（`<!-- -->`）：**
```html
<!-- wzy delete start -->
<!-- <OldTag>content</OldTag> -->
<!-- wzy delete end -->
```

---

## 二、新增或修改代码规范（wzy patch）

在新增代码或对原有代码进行改动的地方，在改动块的最开头加入 `wzy patch start`，末尾加入 `wzy patch end`。

### 格式

```
// wzy patch start
新增或修改的代码
// wzy patch end
```

### 各语言示例

**Java / C / C++ / Kotlin / Go / Swift：**
```java
// wzy patch start
newMethod();
int newVar = 1;
// wzy patch end
```

**Python / Shell / Ruby：**
```python
# wzy patch start
new_function()
new_var = 1
# wzy patch end
```

**HTML / XML：**
```html
<!-- wzy patch start -->
<NewTag>content</NewTag>
<!-- wzy patch end -->
```

---

## 三、综合示例

原有代码被替换为新代码时，两种标记一起使用：

```java
// wzy delete start
// oldMethod(param1);
// wzy delete end
// wzy patch start
newMethod(param1, param2);
// wzy patch end
```

---

## 四、注意事项

1. **不得直接删除**任何原有代码行，必须注释保留并用 `wzy delete` 标记。
2. **所有新增或修改**的代码块都必须用 `wzy patch` 标记包围。
3. 注释符号必须使用**被修改文件对应语言**的注释语法。
4. `start` 和 `end` 标记必须**成对出现**，不得单独使用。
5. 标记注释本身独占一行，不与代码混写在同一行。
