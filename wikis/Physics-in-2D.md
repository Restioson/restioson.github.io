The Box2D physics engine is packaged with Kettle as a dependency. The recommended way to use physics is to use `BodyComponentBuilder` to build a `BodyComponent`, and then to add this to an entity. Direct access to the Box2D `World` is also given.

## Example
```kotlin
this.level.entityEngine.apply {
    addEntity(
            createEntity()
                    .add(BodyComponentBuilder()
                            .withBody(BodyDef.BodyType.yourType)
                            .withBoxFixture(width, height, true)
                            .build(this, this@ContaingClassName.level.world) 
                            
                             // This now refers to the entity engine, as we are in
                             // apply {}. To reference the containing class, use
                             // this@ContainingClassName
                    )
    )
}
```

This prevents memory allocation, though for code not requiring memory allocation one can do the following:
```kotlin
val entity = this.level.entityEngine.createEntity()
val builder = BodyComponentBuilder()

builder
    .withBody(BodyDef.BodyType.yourType)
    .withBoxFixture(width, height, true)
entity.add(builder.build(this.entityEngine, this.level.world))

this.level.entityEngine.addEntity(entity)
```