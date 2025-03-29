# 🧵 Hilosx — Ejemplos prácticos de hilos en Java

Este proyecto contiene ejemplos educativos sobre el uso de **Hilos (Threads)** en Java, abordando conceptos clave como la creación de hilos, sincronización, uso de la interfaz Runnable, comunicación entre hilos y diferencias entre programación imperativa y funcional.

---

## 📂 Estructura del Proyecto

```
Hilosx/
 ┣ 📄 pom.xml → Configuración Maven.
 ┣ 📂 src/main/java/mx/edu/itsescjmra/hilosx/
 ┃ ┣ 📄 Hilos.java → Ejemplo básico de un hilo extendiendo Thread.
 ┃ ┣ 📄 HilosR.java → Ejemplo básico de un hilo usando Runnable.
 ┃ ┣ 📂 Runnable/
 ┃ ┃ ┗ 📄 RunnableSimple.java → Ejemplo sencillo usando Runnable.
 ┃ ┣ 📂 Synchronized/
 ┃ ┃ ┣ 📄 Consumidor.java → Hilo consumidor que consume productos.
 ┃ ┃ ┣ 📄 EjemploProductorConsumidor.java → Ejemplo clásico de Productor-Consumidor usando wait() y notify().
 ┃ ┃ ┣ 📄 EjemploProductorConsumidorJava8.java → Mismo patrón anterior pero usando programación funcional (Java 8).
 ┃ ┃ ┣ 📄 Panaderia.java → Buffer compartido entre productor y consumidor.
 ┃ ┃ ┣ 📄 Panadero.java → Hilo productor.
 ┃ ┣ 📂 threads/
 ┃ ┃ ┗ 📄 ThredSimple.java → Ejemplo básico con la clase Thread.
```

---

## 📝 Descripción de los archivos

| Archivo | Descripción | Tema |
|------|------|------|
| **Hilos.java** | Crea y ejecuta un hilo heredando de la clase Thread. | Creación de hilos con Thread. |
| **HilosR.java** | Crea y ejecuta un hilo implementando Runnable. | Runnable. |
| **RunnableSimple.java** | Ejemplo sencillo usando Runnable. | Runnable. |
| **Consumidor.java** | Hilo consumidor que espera productos. | Comunicación entre hilos. |
| **Panadero.java** | Hilo productor que genera productos. | Comunicación entre hilos. |
| **Panaderia.java** | Buffer compartido que almacena productos. | Sincronización con wait() y notify(). |
| **EjemploProductorConsumidor.java** | Ejemplo clásico del patrón Productor-Consumidor usando programación imperativa. | wait() y notify(). |
| **EjemploProductorConsumidorJava8.java** | Mismo ejemplo anterior pero usando lambdas (programación funcional). | Programación funcional. |
| **ThredSimple.java** | Ejemplo básico de hilo con Thread. | Creación de hilos. |

---

## ❗ Conceptos Importantes

### 🎯 ¿Qué es una Flag?

Una **flag** es una variable booleana que se utiliza como señal para controlar el flujo de un hilo. Por ejemplo, detener un hilo o esperar cierta condición.

```java
private boolean running = true;

public void detener() {
    running = false;
}
```

---

### ⏳ ¿Qué hace el método `wait()`?

El método `wait()` hace que un hilo entre en estado de **espera** y libere el monitor del objeto sincronizado. El hilo queda pausado hasta que otro hilo invoque `notify()` o `notifyAll()`.

```java
synchronized (obj) {
    obj.wait();
}
```

---

### 🚀 ¿Qué hace el método `notify()`?

El método `notify()` despierta **un solo hilo** que está esperando en el monitor del objeto. Es utilizado para notificar que un recurso está disponible o que cierta condición se cumplió.

```java
synchronized (obj) {
    obj.notify();
}
```

---

### ⚔️ Diferencias entre Programación Normal e Instrucciones Funcionales

| Programación Normal (Imperativa) | Programación Funcional |
|----------------------------------|------------------------|
| El código indica **cómo** debe realizarse la tarea, paso a paso. | El código se centra en **qué** se quiere lograr. |
| Usa variables mutables, estados y bucles. | Usa funciones puras, expresiones lambda, Streams. |
| Ejemplo en tu proyecto: `EjemploProductorConsumidor.java` | Ejemplo: `EjemploProductorConsumidorJava8.java` |

---

## ▶️ ¿Cómo ejecutar el proyecto?

1. Clona el repositorio.
```bash
git clone https://github.com/tu-usuario/Hilosx.git
```

2. Entra al proyecto y ejecuta con Maven o tu IDE favorito (IntelliJ, NetBeans, Eclipse).

---

## 👨🏻‍💻 Autor

Proyecto realizado por **PETUCHINI23** como práctica de hilos y sincronización en Java.
