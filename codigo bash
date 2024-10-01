#!/bin/bash

# Mostrar dispositivos activos
echo "=== Verificando dispositivos disponibles ==="
nmcli device status
echo ""

# Listar las redes WiFi disponibles
echo "=== Listando redes WiFi cercanas ==="
nmcli device wifi list
echo ""

# Solicitar al usuario que ingrese el SSID y la contraseña de la red
read -p "Introduce el SSID de la red a la que deseas conectarte: " SSID
read -sp "Introduce la contraseña de la red (si no tiene, solo presiona Enter): " password
echo ""

# Intentar la conexión a la red WiFi
if [ -z "$password" ]; then
    # Si no se ingresó contraseña
    echo "Intentando conectarse a $SSID sin contraseña..."
    nmcli device wifi connect "$SSID"
else
    # Si se ingresó una contraseña
    echo "Intentando conectarse a $SSID con contraseña..."
    nmcli device wifi connect "$SSID" password "$password"
fi

# Verificar si la conexión fue exitosa
echo ""
echo "=== Verificando conexiones activas ==="
nmcli connection show --active
