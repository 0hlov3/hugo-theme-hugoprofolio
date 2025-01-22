+++
title = 'Post 2 - Code Blocks'
date = 2023-02-15T10:00:00-07:00
draft = false
tags = ['red','green']
+++

Anim eiusmod irure incididunt sint cupidatat. Incididunt irure irure irure nisi ipsum do ut quis fugiat consectetur proident cupidatat incididunt cillum. Dolore voluptate occaecat qui mollit laborum ullamco et. Ipsum laboris officia anim laboris culpa eiusmod ex magna ex cupidatat anim ipsum aute. Mollit aliquip occaecat qui sunt velit ut cupidatat reprehenderit enim sunt laborum. Velit veniam in officia nulla adipisicing ut duis officia.

Exercitation voluptate irure in irure tempor mollit Lorem nostrud ad officia. Velit id fugiat occaecat do tempor. Sit officia Lorem aliquip eu deserunt consectetur. Aute proident deserunt in nulla aliquip dolore ipsum Lorem ut cupidatat consectetur sit sint laborum. Esse cupidatat sit sint sunt tempor exercitation deserunt. Labore dolor duis laborum est do nisi ut veniam dolor et nostrud nostrud.

# Yaml
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: nginx
    image: nginx:1.14.2
    ports:
    - containerPort: 80
```

# Bash
```bash
#!/bin/bash
echo "Hello World"
```

# Shell

```shell
kubectl create deployment nginx --image nginx --port 80 --dry-run=client -oyaml 
```
# Go
```Go
package main

import "fmt"

func main() {
    fmt.Println("hello world")
}
```

# Rust
```rust
fn main() {
    println!("Hello World!");
}
```

# Codeblock without Language
```
fn main() {
    println!("Hello World!");
}
```