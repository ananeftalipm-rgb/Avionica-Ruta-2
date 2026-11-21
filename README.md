# Aviónica — Ruta 2: Filtro Pasa-Bajas Sallen-Key (~150 Hz) y Divisor de Voltaje LiPo 2S

**Autora:** Ana Neftali Pérez Montero  
**Carrera:** Ingeniería Aeroespacial (1.er Semestre)  


## ¿Qué hace este proyecto?

Diseñé y simulé un sistema de acondicionamiento de señal analógica para aviónica de dos etapas:
1. **Filtro pasa-bajas activo Sallen-Key (~150 Hz):** Atenúa el ruido de alta frecuencia conservando las señales que nos interesan, alimentado a 3.3 V con el amplificador operacional LT1490, capacitor de desacoplo entre VCC y GND, resistencias de 10k y capacitores de 150nF y 75nF.
2. **Divisor de voltaje para batería LiPo 2S:** Escala el voltaje de la batería (de 6.0 V a 8.4 V) a un rango seguro de aproximadamente 2.03 V a 2.84 V (por debajo del límite de 3.3 V para una lectura segura en ADC), incluyendo filtrado a GND y conectores Conn_01x02.

## Herramientas y versiones usadas

* **KiCad 10.0** (captura esquemática del circuito completo)
* **LTspice v26.1.1** (simulaciones AC de respuesta en frecuencia y simulaciones transitorias)
* **Overleaf / LaTeX** (redacción y compilación del reporte técnico)
* **GitHub Desktop** (control de versiones y publicación en el repositorio)
* **Windows x64**

## Cómo reproducirlo paso a paso

1. **Clonar o descargar el repositorio:**
   Abre **GitHub Desktop**, clona este repositorio a tu equipo y ubica los archivos del esquemático (.kicad_sch), simulaciones (.asc), imágenes y el reporte técnico.
2. **Abrir y revisar el esquemático en KiCad:**
   Abre **KiCad 10.0**, carga el archivo del esquemático del proyecto y verifica las conexiones de alimentación (3.3 V/ GND), etiquetas (VIN_FILTRO, VOUT_FILTRO, VSENSE_ADC), valores de componentes y conectores Conn_01x02.
3. **Ejecutar las simulaciones en LTspice:**
   Abre **LTspice v26.1.1**, carga los archivos .asc correspondientes y corre:
   * El análisis **AC** para comprobar la frecuencia de corte cercana a 150Hz y la atenuación en frecuencias mayores 1kHz.
   * El análisis **transitorio** para revisar la respuesta temporal de las señales (V(n002), V(vout) y el escalamiento del divisor).
4. **Compilar el reporte técnico:**
   Abre el código LaTeX en Overleaf o en tu editor de preferencia, verifica que las imágenes y paquetes (amsmath, graphicx, url, float, geometry) estén en orden y compila para generar el .pdf.
