# IntelliJ Type Renderers

Here are just some simple renderer statements for making debugging more comfortable and accessible :)



## `jdk.internal.org.objectweb.asm.tree.IntInsnNode`

### Render

```java
String.format("%s %d", java.util.Arrays.stream(jdk.internal.org.objectweb.asm.Opcodes.class.getFields()).filter(it ->{try{return java.lang.reflect.Modifier.isStatic(it.getModifiers()) && it.getType() == int.class && (int)it.get(null) == opcode && !it.getName().startsWith("F_") && !it.getName().startsWith("H_") && !it.getName().startsWith("ACC_") && !it.getName().startsWith("T_");}catch(Exception e){return false;}}).findFirst().map(java.lang.reflect.Field::getName).orElse("NOT FOUND") , operand)
```

## `jdk.internal.org.objectweb.asm.tree.LineNumberNode`

### Render

```java
String.format("//line %d", line)
```


## `jdk.internal.org.objectweb.asm.tree.VarInsnNode`

### Render

```java
String.format("%s var%d", java.util.Arrays.stream(jdk.internal.org.objectweb.asm.Opcodes.class.getFields()).filter(it->{try{return java.lang.reflect.Modifier.isStatic(it.getModifiers()) && it.getType() == int.class && (int)it.get(null) == opcode && !it.getName().startsWith("F_") && !it.getName().startsWith("H_") && !it.getName().startsWith("ACC_") && !it.getName().startsWith("T_");}catch(Exception e){return false;}}).findFirst().map(java.lang.reflect.Field::getName).orElse("NOT FOUND"), var)
```


## `jdk.internal.org.objectweb.asm.tree.MethodInsnNode`

### Render

```java
String.format("%s %s.%s%s",java.util.Arrays.stream(jdk.internal.org.objectweb.asm.Opcodes.class.getFields()).filter(it ->{try{return java.lang.reflect.Modifier.isStatic(it.getModifiers()) && it.getType() == int.class && (int)it.get(null) == opcode && !it.getName().startsWith("F_") && !it.getName().startsWith("H_") && !it.getName().startsWith("ACC_") && !it.getName().startsWith("T_");}catch(Exception e){return false;}}).findFirst().map(java.lang.reflect.Field::getName).orElse("NOT FOUND"), owner.replace('/','.'), name, desc)
```


## `jdk.internal.org.objectweb.asm.tree.FieldInsnNode`

### Render

```java
String.format("%s %s.%s", java.util.Arrays.stream(jdk.internal.org.objectweb.asm.Opcodes.class.getFields()).filter(it ->{try{return java.lang.reflect.Modifier.isStatic(it.getModifiers()) && it.getType() == int.class && (int)it.get(null) == opcode && !it.getName().startsWith("F_") && !it.getName().startsWith("H_") && !it.getName().startsWith("ACC_") && !it.getName().startsWith("T_");}catch(Exception e){return false;}}).findFirst().map(java.lang.reflect.Field::getName).orElse("NOT FOUND"), owner.replace('/','.'), name)
```


## `jdk.internal.org.objectweb.asm.tree.LdcInsnNode`

### Render

```java
String.format("%s %s", java.util.Arrays.stream(jdk.internal.org.objectweb.asm.Opcodes.class.getFields()).filter(it ->{try{return java.lang.reflect.Modifier.isStatic(it.getModifiers()) && it.getType() == int.class && (int)it.get(null) == opcode && !it.getName().startsWith("F_") && !it.getName().startsWith("H_") && !it.getName().startsWith("ACC_") && !it.getName().startsWith("T_");}catch(Exception e){return false;}}).findFirst().map(java.lang.reflect.Field::getName).orElse("NOT FOUND"), cst)
```


## `jdk.internal.org.objectweb.asm.tree.JumpInsnNode`

### Render

```java
String.format("%s 0x%s", java.util.Arrays.stream(jdk.internal.org.objectweb.asm.Opcodes.class.getFields()).filter(it ->{try{return java.lang.reflect.Modifier.isStatic(it.getModifiers()) && it.getType() == int.class && (int)it.get(null) == opcode && !it.getName().startsWith("F_") && !it.getName().startsWith("H_") && !it.getName().startsWith("ACC_") && !it.getName().startsWith("T_");}catch(Exception e){return false;}}).findFirst().map(java.lang.reflect.Field::getName).orElse("NOT FOUND") , label.getLabel().toString())
```


## `jdk.internal.org.objectweb.asm.tree.LabelNode`

### Render

```java
String.format("JUMP LABEL %s", label.toString())
```


## `jdk.internal.org.objectweb.asm.tree.FrameNode`

### Render

```java
(this.type==2?"FRAME[type=CHOP{"+this.local.size()+"}]":"FRAME[type="+(this.type==0?"FULL":this.type==1?"APPEND":"SAME")+", "+(this.local==null&&stack==null?"NO CHANGE":((local==null?"Locals=NO CHANGE":"Locals="+java.util.Arrays.toString(local.stream().map(l->l instanceof Integer?java.util.Arrays.stream(jdk.internal.org.objectweb.asm.Opcodes.class.getFields()).filter(it->{try{return java.lang.reflect.Modifier.isStatic(it.getModifiers())&&it.getType()==Integer.class&&(Integer)it.get(null)==l;}catch(Exception e){return false;}}).findFirst().map(java.lang.reflect.Field::getName).orElse("NULL"):l).collect(java.util.stream.Collectors.toList()).toArray()))+(stack==null?", Stack=NO CHANGE":", Stack="+java.util.Arrays.toString(stack.stream().map(s->s instanceof Integer?java.util.Arrays.stream(jdk.internal.org.objectweb.asm.Opcodes.class.getFields()).filter(it->{try{return java.lang.reflect.Modifier.isStatic(it.getModifiers())&&it.getType()==Integer.class&&(Integer)it.get(null)==s;}catch(Exception e){return false;}}).findFirst().map(java.lang.reflect.Field::getName).orElse("NULL"):s).toArray()))))+"]")
```

### Fields

***_LOCALS_***

```java
(local==null?"NO CHANGE":java.util.Arrays.toString(local.stream().map(l->l instanceof Integer?java.util.Arrays.stream(jdk.internal.org.objectweb.asm.Opcodes.class.getFields()).filter(it->{try{return java.lang.reflect.Modifier.isStatic(it.getModifiers())&&it.getType()==Integer.class&&(Integer)it.get(null)==l;}catch(Exception e){return false;}}).findFirst().map(java.lang.reflect.Field::getName).orElse("NULL"):l).collect(java.util.stream.Collectors.toList()).toArray()))
```

***_STACK_***

```java
(stack==null?"NO CHANGE":java.util.Arrays.toString(stack.stream().map(s->s instanceof Integer?java.util.Arrays.stream(jdk.internal.org.objectweb.asm.Opcodes.class.getFields()).filter(it->{try{return java.lang.reflect.Modifier.isStatic(it.getModifiers())&&it.getType()==Integer.class&&(Integer)it.get(null)==s;}catch(Exception e){return false;}}).findFirst().map(java.lang.reflect.Field::getName).orElse("NULL"):s).collect(java.util.stream.Collectors.toList()).toArray()))
```


## `jdk.internal.org.objectweb.asm.tree.AbstractInsnNode`

### Render

```java
java.util.Arrays.stream(jdk.internal.org.objectweb.asm.Opcodes.class.getFields()).filter(it ->{try{return java.lang.reflect.Modifier.isStatic(it.getModifiers()) && it.getType() == int.class && (int)it.get(null) == opcode && !it.getName().startsWith("F_") && !it.getName().startsWith("H_") && !it.getName().startsWith("ACC_") && !it.getName().startsWith("T_");}catch(Exception e){return false;}}).findFirst().map(java.lang.reflect.Field::getName).orElse("NOT FOUND") 
```