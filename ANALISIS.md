# Análisis Técnico — ProyectoLyEP2026

## Hallazgos individuales — Angelo Rosario Abigail

### H21: Actualización de estado en componente desmontado
- **Archivo:** `src/pages/ListaClientes.jsx`
- **Severidad:** Medio
- **Tipo:** Robustez / Ciclo de vida
- **Problema:** El useEffect ejecuta setState después de que el componente se desmonta si el usuario navega antes de que la API responda. Genera memory leak.
- **Solución:** Flag `isMounted` con cleanup en `useEffect`.

### H22: Filtro de búsqueda sin debounce
- **Archivo:** `src/pages/ListaClientes.jsx`
- **Severidad:** Bajo
- **Tipo:** Rendimiento / UX
- **Problema:** El filtro se ejecuta en cada pulsación de tecla, causando re-renders innecesarios.
- **Solución:** `useEffect` con `setTimeout` de 300ms.

### H23: Login sin feedback visual de carga
- **Archivo:** `src/pages/Login.jsx`
- **Severidad:** Medio
- **Tipo:** UX / Feedback
- **Problema:** El botón no se deshabilita durante la autenticación, permitiendo doble submit.
- **Solución:** Estado `cargando` + botón `disabled`.

### H24: Metadata de proyecto inconsistente
- **Archivo:** `package.json`, `src/components/Footer.jsx`
- **Severidad:** Bajo
- **Tipo:** Mantenibilidad
- **Problema:** El package.json decía "pvtrabajointegradorgrupo5" y el Footer "Programación Visual - GRUPO 5".
- **Solución:** Actualizar a "proyecto-lyep-2026-grupo17" y "LyEP 2026 - GRUPO 17".