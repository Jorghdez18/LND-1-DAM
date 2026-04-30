

## 🔹 1. ESTRUCTURA BÁSICA

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">

    <xsl:template match="/">
        <!-- salida HTML -->
    </xsl:template>

</xsl:stylesheet>
🔹 2. PLANTILLA (match)
Raíz del XML
<xsl:template match="/">
Ejemplo real:
<xsl:template match="/">
    <html>
        <body>Hola</body>
    </html>
</xsl:template>
🔹 3. RECORRER NODOS (for-each)
<xsl:for-each select="potencia/registro">
Ejemplo:
<xsl:for-each select="potencia/registro">
    <p>
        <xsl:value-of select="@fecha"/>
    </p>
</xsl:for-each>
🔹 4. ORDENAR (sort)
<xsl:sort select="@fecha" order="ascending"/>
Ejemplo:
<xsl:for-each select="potencia/registro">
    <xsl:sort select="@fecha" order="ascending"/>
    <p><xsl:value-of select="@fecha"/></p>
</xsl:for-each>
🔹 5. SACAR DATOS (value-of)
Elemento
<xsl:value-of select="red"/>
Atributo
<xsl:value-of select="@fecha"/>
Ejemplo completo:
<p>
    <xsl:value-of select="@fecha"/>
</p>
🔹 6. IF (condición simple)
<xsl:if test="red > 0">
Ejemplo:
<xsl:if test="red > 0">
    <p style="color:red;">
        Extracción de red
    </p>
</xsl:if>
🔹 7. IF / ELSE (choose)
<xsl:choose>
    <xsl:when test="condición">
        ...
    </xsl:when>
    <xsl:otherwise>
        ...
    </xsl:otherwise>
</xsl:choose>
Ejemplo:
<xsl:choose>
    <xsl:when test="red > 0">
        <p style="color:red;">Extracción</p>
    </xsl:when>

    <xsl:otherwise>
        <p style="color:green;">Inyección</p>
    </xsl:otherwise>
</xsl:choose>
🔹 8. ESTILOS (CSS en HTML)
Texto rojo
<td style="color:red;">texto</td>
Ejemplo:
<td style="color:red;">
    <xsl:value-of select="red"/>
</td>
Texto verde
<td style="color:green;">
Fondo navy + blanco
<td style="background:navy; color:white;">
Ejemplo:
<td style="background:navy; color:white;">
    <xsl:value-of select="vivienda"/>
</td>
🔹 9. CONCATENAR TEXTO
<xsl:text> hasta </xsl:text>
Ejemplo:
<p>
    <xsl:value-of select="@fecha-inicio"/>
    <xsl:text> hasta </xsl:text>
    <xsl:value-of select="@fecha-fin"/>
</p>
🔹 10. OPERADORES
Operador	Significado
=	igual
>	mayor
<	menor
>=	mayor o igual
<=	menor o igual
Ejemplo:
<xsl:if test="vivienda > 5.5">
    <p>Alto consumo</p>
</xsl:if>
🔹 11. FECHA + HORA
Ejemplo:
<p>
    <xsl:value-of select="@fecha"/>
    <xsl:text> &gt; </xsl:text>
    <xsl:value-of select="@hora"/>
</p>
🔹 12. ATRIBUTOS RAÍZ
potencia/@periodo-inicio
potencia/@periodo-fin
Ejemplo:
<p>
    <xsl:value-of select="potencia/@periodo-inicio"/>
    <xsl:text> hasta </xsl:text>
    <xsl:value-of select="potencia/@periodo-fin"/>
</p>
