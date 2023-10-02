## Diagrama de flujo del reloj digital

```mermaid
flowchart LR

start

    if Configtime pressed then
        if Configtime pressed for > 2s then
            goto ConfiguracionHora
        else
            goto Reloj
        end
    else
        if Time/Alarm pressed then
            if Time/Alarm pressed for > 2s then
                goto Alarma
            else
                goto Reloj
            end
        else
            if Time/Stopwatch pressed then
                if Time/Stopwatch pressed for > 2s then
                    goto Cronometro
                else
                    goto Reloj
                end
            else
                goto Reloj
            end
        end
    end

ConfiguracionHora
    if Min/Stop pressed then
        if Hora/Star pressed then
            if Hora/Star pressed for > 2s then
                goto Reloj
            else
                goto ConfiguracionHora
            end
        else
            goto ConfiguracionHora
        end
    else
        goto Reloj
    end

Alarma
    if Min/Stop pressed then
        if Hora/Star pressed then
            if Hora/Star pressed for > 2s then
                goto Reloj
            else
                goto Alarma
            end
        else
            goto Alarma
        end
    else
        goto Reloj
    end

Cronometro
    if Min/Stop pressed then
        if Hora/Star pressed then
            if Hora/Star pressed for > 2s then
                goto Reloj
            else
                goto Cronometro
            end
        else
            goto Cronometro
        end
    else
        if Clear pressed then
            goto Reloj
        else
            goto Cronometro
        end

end


Este código mostrará el diagrama de flujo en GitHub como una imagen.

También puedes usar un servicio de alojamiento de diagramas de flujo, como MermaidJS, para generar una imagen del diagrama de flujo y luego agregarla a tu archivo README.md.
