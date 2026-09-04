---
layout: page
title: Unidad 1 — Introducción a Android
---

# Unidad 1 — Introducción a Android

## Contenidos

- Arquitectura de una app Android
- El ciclo de vida de una Activity
- Estructura de un proyecto en Android Studio

## Ejemplo de código

```kotlin
class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
    }
}
```

<div class="ejercicio" markdown="1">
**Ejercicio 1.1** — Añade un `Button` al layout y muestra un `Toast` con un mensaje al pulsarlo.
</div>

[Volver al inicio](../){: .btn}
