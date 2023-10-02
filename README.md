
```mermaid
sequenceDiagram

participant Reloj
participant Alarma
participant Cronometro

Reloj -> Reloj: Iniciar
Reloj -> Display: Mostrar hora actual

loop

Reloj -> Alarma: Revisar hora de alarma

if alarma activa

Reloj -> Alarma: Activar alarma

else

Reloj -> Display: Mostrar hora actual

end

Reloj -> Cronometro: Revisar estado del cronómetro

if cronómetro activo

Reloj -> Cronometro: Actualizar tiempo del cronómetro

if cronómetro detenido

Reloj -> Display: Mostrar hora actual

end

end

Reloj -> Usuario: Esperar evento

User -> Reloj: Presionar botón de configuración de hora
Reloj -> Reloj: Entrar en modo de configuración de hora
Reloj -> Display: Mostrar hora actual

loop

User -> Reloj: Presionar botón de hora
Reloj -> Reloj: Cambiar hora
Reloj -> Display: Mostrar hora configurada

end

Reloj -> Reloj: Salir del modo de configuración de hora
Reloj -> Display: Mostrar hora actual

User -> Reloj: Presionar botón de alarma
Reloj -> Reloj: Entrar en modo de configuración de alarma
Reloj -> Display: Mostrar hora actual

loop

User -> Reloj: Presionar botón de hora
Reloj -> Reloj: Cambiar hora de alarma
Reloj -> Display: Mostrar hora configurada

end

Reloj -> Reloj: Salir del modo de configuración de alarma
Reloj -> Display: Mostrar hora actual

User -> Reloj: Presionar botón de cronómetro
Reloj -> Reloj: Entrar en modo de cronómetro
Reloj -> Display: Mostrar hora actual

loop

User -> Reloj: Presionar botón de hora
Reloj -> Cronometro: Iniciar cronómetro
Reloj -> Display: Mostrar hora del cronómetro

if cronómetro detenido

Reloj -> Display: Mostrar hora actual

end

User -> Reloj: Presionar botón de hora
Reloj -> Cronometro: Detener cronómetro
Reloj -> Display: Mostrar hora del cronómetro

User -> Reloj: Presionar botón de hora
Reloj -> Cronometro: Reiniciar cronómetro
Reloj -> Display: Mostrar hora del cronómetro

end

Reloj -> Reloj: Salir del modo de cronómetro
Reloj -> Display: Mostrar hora actual

end
