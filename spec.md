# 🍫 Double Chocolate Cone (Double C*) — Official Language Specification (v1)

## 1. Overview
Double Chocolate Cone (Double C*) is a game‑focused scripting language designed for the ConeEngine ecosystem.  
It is simple for beginners, powerful for advanced users, and transpiles to JavaScript.

**File extension:**  
.dc*

---

## 2. Syntax

### 2.1 Basic Structure
A Double C* script contains:
- entities
- scenes
- events
- variables
- actions

Example:
entity Player {
    var speed = 6

    on start {
        print "Player loaded"
    }

    on update {
        if key W {
            move(0, -speed)
        }
    }
}

### 2.2 Blocks
Blocks use `{ }`.  
Indentation is optional but recommended.

### 2.3 Comments
# This is a comment

### 2.4 Strings
"Hello world"

### 2.5 Numbers
10  
3.14  
-5

### 2.6 Booleans
true  
false

### 2.7 Vectors
(1, 2)  
(0, 5, 0)

---

## 3. Keywords

### Entity & Scene
entity  
scene  
spawn  
destroy  

### Variables
var  

### Events
on  
start  
update  
click  
collide  
key  
load  

### Logic
if  
else  

### Actions
move  
jump  
rotate  
print  

---

## 4. Grammar (EBNF)

program        = { entity | scene } ;

entity         = "entity" identifier "{" { member } "}" ;
scene          = "scene" identifier "{" { sceneMember } "}" ;

member         = variable | event ;
sceneMember    = spawnStmt ;

variable       = "var" identifier "=" expression ;

event          = "on" identifier "{" { statement } "}" ;

spawnStmt      = "spawn" identifier "at" vector ;

statement      = actionStmt | ifStmt | expressionStmt ;

actionStmt     = identifier "(" [ arguments ] ")" ;
ifStmt         = "if" expression block [ "else" block ] ;
expressionStmt = expression ;

expression     = literal | identifier | binaryExpr | callExpr ;

binaryExpr     = expression operator expression ;
callExpr       = identifier "(" [ arguments ] ")" ;

arguments      = expression { "," expression } ;

literal        = number | string | boolean | vector ;
vector         = "(" number { "," number } ")" ;

identifier     = letter { letter | digit | "_" } ;

---

## 5. Events

### Built‑in events:
on start  
on update  
on click  
on collide(other)  
on key KEYNAME  
on load  

Example:
on collide(other) {
    print "Hit something!"
}

---

## 6. Data Types

number  
string  
boolean  
vector2  
vector3  
entity reference  

---

## 7. Runtime API (ConeEngine)

### Movement
move(x, y)  
move(x, y, z)

### Jump
jump(force)

### Rotation
rotate(x, y, z)

### Spawning
spawn EntityName at (x, y)  
spawn EntityName at (x, y, z)

### Destroy
destroy(entity)

### Logging
print("text")

### Input
key W  
key SPACE  

---

## 8. File Extension
.dc*

Example file:
player.dc*

---

## 9. Example Full Program

entity Player {
    var speed = 6
    var jumpForce = 12

    on start {
        print "Player ready!"
    }

    on update {
        if key W {
            move(0, -speed)
        }
        if key SPACE {
            jump(jumpForce)
        }
    }
}

scene Level1 {
    spawn Player at (0, 0)
}
