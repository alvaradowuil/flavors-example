## Product Flavors

Los **productFlavors** nos permiten tener diferentes variantes de un mismo producto de forma sencilla. Usando product flavors podríamos tener un mismo proyecto y de este generar diferentes aplicaciones. Por ejemplo, tener un solo proyecto del cual se genere una aplicación de paga y una aplicación gratuita en donde solo algunas funcionalidades hacen la diferencia. Otro ejemplo es tener un solo proyecto y de este generar aplicaciones para diferentes clientes en donde lo único que hace la diferencia es la interfaz gráfica.

Este repositorio muestra un ejemplo sencillo. El desarrollo de una aplicación para dos clientes diferentes, **Los Aliens** y **Los Zombies**, ambas aplicaciones con la misma funcionalidad (Buscar humanos para alimentarse) pero con diferente diseño.

![Aliens_Zombies](https://user-images.githubusercontent.com/4116286/124367691-e851d380-dc16-11eb-9cb9-3e0f2b79732c.jpg)

# Configurar productFlavors
Debes editar el archivo build.gradle del módulo de tu aplicación de la siguiente manera.

```
flavorDimensions "default"
productFlavors {
    aliens {
        applicationIdSuffix ".aliens"
    }
    zombies {
        applicationIdSuffix ".zombies"
    }
}
```

Es recomendable que cada product flavor tenga un nombre representativo de la variación del producto. En este caso **aliens** y **zombies**, que son los clientes interesados. el atributo **applicationIdSuffix** define el aplicationId para cada una de las aplicaciones. En este caso toma el paquete principal y le agrega el sufijo aliens y zombies. Así ambos tendrán diferente applicationId.

# Build Variants
Para debuguear cada una de tus variantes en Android Studio simplemente activa la pestaña Build Variants y selecciona la variante que te interesa.

![BuildVariants](https://user-images.githubusercontent.com/4116286/124367817-eb998f00-dc17-11eb-8ca5-6cd151284b83.jpg)

# Variantes en la aplicación
La aplicación para Aliens y la aplicación para Zombies solo tienen diferencia de imágenes, colores y textos por lo que definiremos estos recursos para cada variante.

En la ruta app -> src crearemos un directorio para cada flavor con el mismo nombre con el que los definimos en buil.gradle.

![source](https://user-images.githubusercontent.com/4116286/124367847-18e63d00-dc18-11eb-8663-ed4fe1af9555.jpg)

Dentro de cada directorio definimos los directorios y ficheros que necesitamos, en nuestro caso el directorio res y los recursos que varían para cada flavor.

![diff](https://user-images.githubusercontent.com/4116286/124367856-34e9de80-dc18-11eb-8a36-f15753e36efa.jpg)

# Ver
[Product Flavors](https://developer.android.com/studio/build/build-variants)



