import streamlit as st
import pandas as pd

# Configura el título y presenta la aplicación de Kampus+.
st.set_page_config(page_title="Calculadora de ventas | Kampus+", page_icon="🛍️")
st.title("Calculadora de ventas de Kampus+")
st.write("Calcula cuánto recibe un vendedor después de la comisión de la plataforma.")

# Solicita los datos de una venta; los valores iniciales son ejemplos hipotéticos.
precio = st.number_input("Precio de cada producto (S/)", min_value=0.0, value=25.0, step=1.0)
unidades = st.number_input("Cantidad de productos vendidos", min_value=1, value=2, step=1)
comision = st.slider("Comisión de Kampus+ (%)", min_value=0, max_value=20, value=5)

# Calcula el importe total, la comisión y el monto neto para el vendedor.
total = precio * unidades
monto_comision = total * comision / 100
neto = total - monto_comision

# Muestra el resultado principal con métricas fáciles de interpretar.
st.subheader("Resultado de la venta")
st.metric("Total de la venta", f"S/ {total:,.2f}")
st.metric("Comisión de Kampus+", f"S/ {monto_comision:,.2f}")
st.metric("Recibe el vendedor", f"S/ {neto:,.2f}")

# Organiza el detalle del cálculo en una tabla.
detalle = pd.DataFrame({
    "Concepto": ["Precio por producto", "Unidades", "Comisión (%)", "Total de venta", "Comisión descontada", "Pago al vendedor"],
    "Valor": [f"S/ {precio:,.2f}", int(unidades), f"{comision}%", f"S/ {total:,.2f}", f"S/ {monto_comision:,.2f}", f"S/ {neto:,.2f}"]
})
st.subheader("Detalle del cálculo")
st.dataframe(detalle, hide_index=True, use_container_width=True)

# Aclara que los datos precargados son solo una demostración.
st.caption("Ejemplo hipotético. La comisión puede modificarse para probar distintos escenarios.")
