# IE0405 Modelos Probabilísticos de Señales y Sistemas
# Laboratorio 4
## Kevin Morales Salas
### B64816
Para la solución de este laboratorio, el profesor brindó un código base para la solución del problema 2 de la práctica correspondiente a la lección 13,
como la solución para el problema 1 de la misma práctica es similar, se usa este código modificando sólo lo necesario para obtener la solución para este problema 1.

Para este problema, se redefinieron las variables A y Z con distribución gaussiana y con valores apropiados para que tuvieran media y varianza:

```python
        vaA = stats.norm(0, np.sqrt(10))
        vaZ = stats.norm(0, np.sqrt(10))
```

Luego se define la constante $\omega_{0}$:

```python
        w0 = 6 # Elegí este número porque es mi favorito
```

Ahora sigue las N realizaciones a modificar de la función $X(t)$:

```python
        for i in range(N):
	        A = vaA.rvs()
	        Z = vaZ.rvs()
	        x_t = (A * np.cos(np.pi*t + Z)) + (Z*np.sin(w0*t))
	        X_t[i,:] = x_t
	        plt.plot(t, x_t)
```

Finalmente se modifica el valor teórico de la correlación:

```python
        Rxx = P * np.cos(w0*taus) # Donde P es el promedio de X que es igual al promedio de Y
```

Para esta documentación sólo se escribieron los cambios realizados al código dado, lo demás quedó igual (incluso el código para los gráficos). Algunas partes se
eliminaron debido a que no eran necesarias.
