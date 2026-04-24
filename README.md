# Reporte de Actividad — Redes Neuronales (U-NET)

**Nombre:** Sergio Lara  

---

## Descripción

Actividad práctica con Stable Diffusion (`CompVis/stable-diffusion-v1-4`), explorando el comportamiento de la U-Net en el proceso de difusión inversa mediante tres experimentos controlados.

**Prompt utilizado:**  
`"A futuristic cup of coffee, neon glowing liquid, highly detailed"`

---

## Experimento A — Pasos de denoising (U-Net)

Se varió el número de pasos de inferencia manteniendo fija la escala de guía (`7.5`) y la semilla (`42`).

| Pasos | Archivo guardado      |
|-------|-----------------------|
| 1     | `A1_pasos_1.png`      |
| 10    | `A2_pasos_10.png`     |
| 25    | `A3_pasos_25.png`     |
| 50    | `A4_pasos_50.png`     |

**Observación:** A mayor número de pasos, la U-Net tiene más iteraciones para eliminar ruido, produciendo imágenes más detalladas y coherentes.

---

## Experimento B — Escala de guía / Obediencia (CLIP)

Se varió la escala de guía (`guidance_scale`) manteniendo fijos los pasos (`25`) y la semilla (`42`).

| Escala | Archivo guardado          |
|--------|---------------------------|
| 1      | `B1_obediencia_1.png`     |
| 7.5    | `B2_obediencia_7_5.png`   |
| 30     | `B3_obediencia_30.png`    |

**Observación:** Con escala baja el modelo ignora casi por completo el prompt; con escala alta, se sobreajusta y la imagen puede saturarse o distorsionarse.

---

## Experimento C — Semilla / Espacio Latente

Se varió la semilla del generador para explorar distintos puntos del espacio latente, manteniendo constantes el prompt, los pasos (`25`) y la escala (`7.5`).

| Semilla | Archivo guardado         |
|---------|--------------------------|
| 42      | `C1_semilla_42.png`      |
| 100     | `C2_semilla_100.png`     |
| 999     | `C3_semilla_999.png`     |

**Observación:** Cada semilla inicializa un ruido gaussiano diferente, lo que produce composiciones visuales distintas a pesar de usar el mismo prompt.

---

## Conclusión

Los tres parámetros (pasos, escala de guía y semilla) permiten controlar aspectos distintos de la generación: calidad de denoising (U-Net), adherencia al texto (CLIP) y variabilidad compositiva (espacio latente).

---

**Repositorio GitHub:** [Insertar enlace a tu rama aquí]
