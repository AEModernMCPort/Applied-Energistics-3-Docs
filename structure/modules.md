# Modules

## Concept

Applied Energistics 3 is split into modules. Each module represents a certain theme/feature/element/..., like _World Gen_ module is responsible for world generation (meteorites and ores), _ME_ module adds ME system, _Spatial IO_ module adds spatial storage cells, etc.
The significant part of the new modules system is difference between _internal_ and _external_ modules. Before we get to it, you have to understand how Applied Energistics 3 will be distributed:
- There will be one JAR that includes ALL modules (it will also be the one you download by default).
- A _Core_ jar which contains utility classes, core API and all internal modules. It is included in the _ALL_ JAR, but in other cases it will always have to be installed.
- A JAR per external module, which logically requires _Core_ JAR to be installed.
- Some JARs for addon & cross-compat developers, which we will not cover here.

Now that we covered distribution, we only have to sum things up to define _internal_ and _external_ modules:
- _Internal_ modules - Modules of Applied Energistics 3 that are always installed, whether you want it or not.
- _External_ modules - Optional Applied Energistics 3 modules.

## Code

Modules is the core system of Applied Energistics 3. All systems begin in modules. Without them, nor API can't do anything, nor AE3 itself can't do anything.

{% method %}

{% common %}

## Retrieving module instances

If you want to do anything with modules (AE3 in general), you gotta retrieve their instance first.

{% sample lang="api" %}

Use [`@Module.Instance(String)`](https://github.com/AEModernMCPort/Applied-Energistics-3/blob/codename-andromeda/src/api/java/appeng/api/module/Module.java#L82) on a static field to populate it with instance of the module, the `value` parameter being the name of the module.

Example code:
```java
@Module.Instance("core")
public static ICore core;
```
This will populate the `core` field with the instance of core module.

Modules are instatiated by AE during pre initialization. If you have to access modules' instances during pre initilization, make sure to add `after:appliedenergistics3` to your `@Mod` dependencies.

Note: Toposearch is in the to-do list. Once it will be implemented, following code (for previous example) will become valid:
```java
@Module.Instance
public static ICore core;
```

{% sample lang="internal" %}

Use `ModuleInternalClass#INSTANCE` to retrieve module's instance.
Example code:
```java
AppEngCore.INSTANCE.definitions(...)
```
This will invoke `definitions` method on the instance of core module.

{% endmethod %}

### Current Modules Structure:
**(All modules under _Core_ are internal)**

- Core
  - Crafting
  - ME
  - Spatial
  - World Gen
- Debug (not distributed)
- Decorative
- Miscellaneous
- Tools