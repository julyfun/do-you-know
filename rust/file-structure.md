创建文件夹意味着对 mod 的文件化。

原本有 mod:

```rust
mod house {
    mod mather {}
    pub mod father { 
        fn hold() { super::house_hold(); }
    }
    fn house_hold() {}
}
```

...呃，现在准备把 mod house 做成一个文件。

这是肯定要的，in main.rs:

```rs
mod house;
```

然后：

```rs
touch house.rs
```

...呃，现在准备把 mod house 做成一个文件夹。

```sh
mkdir house
touch house/mather.rs
touch house/father.rs
```

光做这个文件夹确实没法复现 `fn house_hold()` 以及 `pub mod` 吼。

本质上是因为 mod 完全具有描述功能而文件夹只能表示节点的存在性，不能描述任何内容.

在 house.rs 你应该描述 mod 的全部内容。

