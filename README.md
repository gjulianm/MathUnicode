## MathUnicode para LaTeX - Mac

Este repositorio consta de dos archivos, basados en [una respuesta](http://tex.stackexchange.com/questions/110042/entering-unicode-math-symbols-into-latex-direct-from-keyboard-on-a-mac#110043) de Jon Wickerson en TeX - StackExchange. 

### MathUnicode.sty

Este archivo define los códigos Unicode de los caracteres para que LaTeX los reconozca. Aunque algunos como µ o ∂ los reconoce sin problemas, para el resto hay que especificar a qué carácter nos referimos. Como cualquier paquete LaTeX, hay que copiarlo al directorio de paquetes y después ejecutar `texhash`. Unos comandos para hacerlo de forma rápida:

```
latex_dir=$(dirname $(kpsewhich article.cls))
cp -v MathUnicode.sty $latex_dir
sudo texhash
```

### SpanishMathUnicode.keylayout

Basándome en el layout que Wickerson publicó pero adaptado a un teclado español. Las letras griegas son las que uno esperaría (α está en `alt-a`, β en `alt-b`...), y otros símbolos están puestos en otros sitios con cierto sentido. En las imágenes se ve la distribución completa y me dejo de cháchara.

![Modificadores con alt](images/SpanishMathUnicode-Alt.png?raw=true)
![Modificadores con alt-shift](images/SpanishMathUnicode-AltShift.png?raw=true)

Además, hay dos modos para introducir flechas de una o dos líneas. Se activan con `alt-shift- -` y `alt-=`, y permiten introducir flechas usando las teclas *wasd*:

![Estado -](images/KeyStateDash.png?raw=true)
![Estado =](images/KeyStateEqual.png?raw=true)

Para instalarlo, hay que copiarlo o bien a `~/Library/Keyboard Layouts` (para el usuario local) o a `/Library/Keyboard Layouts` si se quiere instalar de forma global. Después hay que salir de la sesión para que OS X reconozca el layout y seleccionarlo en _Preferencias de teclado -> Fuentes de entrada_.


