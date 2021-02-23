# Proyecto-parcial1-AguilarA

_ **PROYECTO PRIMER PARCIAL** _

Proyecto primer parcial, compartiremos todo lo aprendido durante este parcial, y esto es lo que nos pide el proyecto: Modelo Lambert Wrap, Phong, Rim Light, Banded, Ramp Texture, Normal Map, Normal Strength.

El proyecto contiene lo siguiente:

El Shader es lo que da color y para crear este archivo es necesario tener una estructura de código con propiedades, un SubShader que contenga Tags, y afuera de este un CGPROGRAM y ENDCG.

Albedo: Color sin ninguna alteración, natural.

Lambert Wrap es el modelo de iluminación más básico y hace uso de un fall off.

Phong funciona para crear un efecto de brillo, determina un SpecularColor, SpecularPower, SpecularGloss y GlossSteps. Hace uso del producto punto entre la normal y la dirección de la luz, pero también se crea una variable reflectedLight para obtener una segunda dirección de la luz que sería el reflejo. Ocupa el RdotL y la Specularity.

Normal Map es para agregar una textura, por lo que necesita un MainTex tipo 2D.

Normal Strength agrega una textura de normales y requiere de un Normal Texture y un Normal Strength. En el void surf se pone el texColor, normalColor y la normal.

Rim Light es para que se de un efecto de iluminación solamente en las orillas, contiene un RimColor con HDR para mejor definición y un RimPower. En el void surf de agrega el nVwd, para normalizar la dirección por donde se aprecia, el NdotV y el rim para controlar su saturación.

Ramp Texture es de tipo 2D y es muy similar al banded, solo que en este se le agrega una imagen en escala de grises dependiendo el modelo.

Banded es para que tenga una iluminación con estilo de anillos entre blanco hasta el negro, necesita de steps tipo rango para controlar la cantidad de veces que se apreciara en el modelo 3D.
