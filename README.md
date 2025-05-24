# 🔧 MC-Build Utilities

A few handy utilities and libraries for [MC-Build](https://mcbuild.dev/)

# 📋 Templates

## `score.mcbt`

Simple shorthand templates for scoreboard operations.

### Constant Operations

Set the value of a score to a constant.

```
set <name> <objective> <value>

>>> scoreboard players set <name> <objective> <value>
```

Get the value of a score.

```
get <name> <objective> <value>

>>> scoreboard players get <name> <objective>
```

Add a constant value to a score.

```
add <name> <objective> <value>

>>> scoreboard players add <name> <objective> <value>
```

Subtract a constant value from a score.

```
sub <name> <objective> <value>

>>> scoreboard players remove <name> <objective> <value>
```

Multiply a score by a constant value.

```
mul <name> <objective> <value>

>>> scoreboard players operation <name> <objective> *= <value>
```

Divide a score by a constant value.

```
div <name> <objective> <value>

>>> scoreboard players operation <name> <objective> /= <value>
```

### Variable Operations

Perform a scoreboard operation on a score holder using a constant.

```
op <target> <targetObjective> <operation> <constant>

>>> scoreboard players operation <target> <targetObjective> <operation> <constant> <internalMCBObjective>
```

Perform a scoreboard operation on a score holder using another score holder.

```
op <target> <targetObjective> <operation> <source> <sourceObjective>

>>> scoreboard players operation <target> <targetObjective> <operation> <source> <sourceObjective>
```

Omitting the sourceObjective will use the targetObjective in it's place.

```
op <target> <targetObjective> <operation> <source>

>>> scoreboard players operation <target> <targetObjective> <operation> <source> <targetObjective>
```

## `sequence.mcbt`

Runs a scheduled sequence of functions in order.

```
function foo {
	sequence {
		say "Hello, world!"
		wait 1s
		say "One second later..."
		wait 1s
		say "Two seconds later..."
		wait 1s
		say "Goodbye, world!"
	}
}

```

Result:

```
say "Hello, world!"
schedule function namespace:zzz/0 20t
schedule function namespace:zzz/1 40t
schedule function namespace:zzz/2 60t
```
