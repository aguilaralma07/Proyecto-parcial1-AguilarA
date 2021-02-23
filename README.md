# Proyecto-parcial1-AguilarA

**PROYECTO PRIMER PARCIAL**

Proyecto primer parcial, compartiremos todo lo aprendido durante este parcial, y esto es lo que nos pide el proyecto: Modelo Lambert Wrap, Phong, Rim Light, Banded, Ramp Texture, Normal Map, Normal Strength.

El proyecto contiene lo siguiente:

**Shader**  es lo que da color y para crear este archivo es necesario tener una estructura de código con propiedades, un SubShader que contenga Tags, y afuera de este un CGPROGRAM y ENDCG.

**Albedo:**  Color sin ninguna alteración, natural.

**Lambert Wrap**  es el modelo de iluminación más básico y hace uso de un fall off.

  - **Producto punto/escalar (dot):** Multiplica el producto de los módulos por el coseno del ángulo.
  - **Falloff:**  La caída de la sombra y en que magnitud va a ser. Llega la luz se esparce hasta que se ve negro. Se calcula por medio de la normal, con el producto punto ---\&gt; dot, El producto punto entre la normal y la dirección de la luz ---\&gt; N dot L

**Phong**  funciona para crear un efecto de brillo, determina un SpecularColor, SpecularPower, SpecularGloss y GlossSteps. Hace uso del producto punto entre la normal y la dirección de la luz, pero también se crea una variable reflectedLight para obtener una segunda dirección de la luz que sería el reflejo. Ocupa el RdotL y la Specularity.

  - **SpecularColor:**  Es para el color de la luz del brillo.
  - **SpecularPower:**  Que tan fuerte es el efecto del brillo.
  - **RdotL:**  Reflejo producto punto de viewDir, esto regresa el difuso.
  - **viewDir:**  De donde está viendo el espectador al objeto, se ocupa ya que depende de donde se visualice la luz puede cambiar.
  - **Specularity:**  Es el aspecto visual de los reflejos especulares.

- **SpecularGloss:**  lo amplio es el efecto del brillo.

  - **GlossSteps:**   agranda los pasos que le toma al llegar al punto más amplio, también sirve para ahorrar memoria.

**Normal Map**  es para agregar una textura, por lo que necesita un MainTex tipo 2D.

**Normal Strength**  agrega una textura de normales y requiere de un Normal Texture y un Normal Strength. En el void surf se pone el texColor, normalColor y la normal.

**Rim Light**  es para que se de un efecto de iluminación solamente en las orillas, contiene un RimColor con HDR para mejor definición y un RimPower. En el void surf de agrega el nVwd, para normalizar la dirección por donde se aprecia, el NdotV y el rim para controlar su saturación.

  - **RimColor:**  El color de la iluminación de la orilla.
  - **RimPower:**  La intensidad de la iluminación de la orilla.
  - **Normalize:**  Aquí lo importante es la dirección y si lo pasa a 0 y 1.
  - **Saturate:**  Devuelve el menor número entero no menor que un escalar o cada componente del vector.
  - **Emission:**  Controla la cantidad de color que una superficie emite desde su material.

**Ramp Texture**  es de tipo 2D y es muy similar al banded, solo que en este se le agrega una imagen en escala de grises dependiendo el modelo.

**Banded**  es para que tenga una iluminación con estilo de anillos entre blanco hasta el negro, necesita de steps tipo rango para controlar la cantidad de veces que se apreciara en el modelo 3D.

  - **lightBandsMultiplier:**  Decide cuantas bandas va a haber.
  - **lightBandsAdditive:**  Es con el que se le da color o con el que va a sumar más que nada la separación entre las líneas.
  - **bandedLightModel:**  Sirve para ya hacer la operación que mostrará al número de pasos.
  - **floor:**  Redondea al número entero más cercano.
# Proyecto-parcial1-AguilarA
