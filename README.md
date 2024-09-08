- 👋 Hi, I’m @lara-abril
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
lara-abril/lara-abril is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

#pip install streamlit

import streamlit as st

# Título de la app
st.title("Calculadora de Ventas y Comisiones")

# Pedimos al usuario que ingrese las ventas
ventas = st.text_input("Ingrese las ventas separadas por comas (ejemplo: 30000, 45000, 23000, 38000)")

# Convertimos la entrada en una lista de números
if ventas:
    ventas_list = [int(v) for v in ventas.split(",")]
    comisiones = []
    
    # Calculamos la comisión
    for venta in ventas_list:
        if 20000 <= venta <= 30000:
            comision = venta * 0.03  # Comisión del 3%
        elif venta > 30000:
            comision = venta * 0.05  # Comisión del 5%
        else:
            comision = 0
        comisiones.append(comision)

    # Mostramos las comisiones
    st.write(f"Comisiones: {comisiones}")
