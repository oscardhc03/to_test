
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
