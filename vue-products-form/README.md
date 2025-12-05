# 🧪 **SIMULADOR PRUEBA PRÁCTICA – Vue.js (50 pts)**

**Tema:** Gestión de productos con componentes, validación, tabla dinámica y mensajes.

---

# 🎯 **ENUNCIADO**

Debes desarrollar una pequeña aplicación en Vue.js que permita:

1. **(10 pts)** Registrar productos mediante un formulario.
2. **(10 pts)** Mostrar la lista de productos en una **tabla** con diseño limpio.
3. **(10 pts)** Aplicar **validaciones** en el formulario (sin alertas).
4. **(10 pts)** Desplegar **mensajes de éxito y error** estilo UI.
5. **(10 pts)** La aplicación debe estar correctamente **componentizada**:

### Componentes obligatorios:

1. `ProductoForm.vue` → formulario para agregar productos
2. `ProductoTabla.vue` → tabla que muestra todos los productos
3. `ProductosView.vue` → componente padre que gestiona la lógica
4. `App.vue` → capa principal donde se monta todo

---

# 📝 **REQUISITOS DETALLADOS**

## 🔹 **1. Formulario – ProductoForm.vue (10 pts)**

Debe contener:

* Campo: **Nombre del producto**
* Campo: **Precio**
* Botón: **Agregar producto**

Validaciones:

* Ambos campos obligatorios
* El precio debe ser un número mayor que 0

Mensajes:

* Mostrar mensaje de error si falta info
* Mostrar mensaje de éxito cuando se agregue

No se permite usar `alert`.

---

## 🔹 **2. Tabla – ProductoTabla.vue (10 pts)**

Debe:

* Mostrar los productos en una tabla con:

  * Nombre
  * Precio
* Tener diseño (bordes, centrado, colores suaves)

---

## 🔹 **3. Comunicación entre componentes (10 pts)**

El formulario debe emitir un evento:

```
this.$emit('agregar-producto', producto)
```

El componente `ProductosView.vue` debe:

* Recibir el producto
* Insertarlo en un array
* Enviarlo a la tabla como prop

---

## 🔹 **4. Validaciones + Mensajes (10 pts)**

Los mensajes deben aparecer debajo del formulario y ocultarse automáticamente después de 2–3 segundos.

---

## 🔹 **5. Organización y estilo general (10 pts)**

Se evaluará:

* Limpieza del código
* Uso de `<style scoped>`
* Estructura clara
* Componentes bien separados
* Código legible y sin repetición innecesaria

---

# 🧩 **ENTREGA ESPERADA**

Tú debes enviarme:

✔ El código completo de:

* `App.vue`
* `ProductosView.vue`
* `ProductoForm.vue`
* `ProductoTabla.vue`

Y yo te lo **corregiré** y te daré **nota sobre 50 pts + retroalimentación profesional**.

