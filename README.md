# Quantum-Simulator

# Simulacion de Estados de Bell con Qiskit #

Este repositorio documenta la implementación y ejecución práctica de circuitos cuánticos para generar el **Estado de Bell** utilizando el entorno de desarrollo **Qiskit** de IBM y simuladores estadísticos de computacion clásica.

---

### 1. Creación y Estructura del Estado entrelazado
En esta primera etapa se construye la lógica cuántica pura para poner el sistema en máxima correlación.

* **Código de Inicialización :** 'QuantumCircuit(2)' (2 cúbits ).
* **Puertas Lógicas Aplicadas:**
* *'h(0)': Compuerta **Hadamar** sobre el cúbit 0 para introducirlo a la superposición perfecta.
* *'cx(0, 1)': Compuerta **Controlled-x (CNOT)** para entrelazar ambos estados.
* **Estado Cuántico Resultado: Se obtiene matematicamente el estado entrelazado, $|\Phi^+\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)$, donde el estado de un cúbit depende del otro.

### 2. Flujo Completo: Medición, Simulación e Histograma
En esta celda se mapea el comportamiento cuántico a la memoria clasica del computador mediante muestreos repetitivos para analizar sus resultados.

* **Arquitectura de Memoria :** 'QuantumCircuit(2, 2)' (2 cúbits y 2 bits clásicos)
* **Lógica de Ejecucion:**
* 'measure([0, 1], [0, 1])': Instruccion de medición que obliga a los cúbits a colapsar, mapeando el resultado fisico.
* 'AerSimulator()': Instanciacion del simulador local de Qiskit Aer para emular el procesador cuántico ideal.
* 'Simulador.run(circuito).result().get_counts()': Ejecución automática del circuito a lo largo de 1024 (*shots*) independientes para recolectar las frecuencias de salida.
* **Análisis Estadístico del Histograma:**
* **Estado 00:** 529 conteos.
* **Estado 11:** 495 conteos.
* **Interpretación:** Los estados validan una distribución probabilistica al **50% / 50%**.

---
