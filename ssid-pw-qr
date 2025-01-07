# Get the current SSID
SSID=$(system_profiler SPAirPortDataType | awk '/Current Network Information:/ {getline; print $1}' | sed 's/Network//g' | tr -d ':' | xargs)

# Retrieve the password
PASSWORD=$(security find-generic-password -wga "$SSID")

# Retrieve the security type
SECURITY=$(/System/Library/PrivateFrameworks/Apple80211.framework/Versions/Current/Resources/airport -I | awk -F': ' '/^ *Security/ {print $2}')

# Adjust the security type for the QR code
case "$SECURITY" in
  "WPA2 Personal") SECURITY="WPA";;
  "WEP") SECURITY="WEP";;
  "None") SECURITY="nopass";;
  *) SECURITY="WPA";;
esac

# Output network information
echo "SSID: $SSID"
echo "Password: $PASSWORD"
echo "Security: $SECURITY"

# Generate QR code for WiFi access
qrencode -t ANSIUTF8 "WIFI:T:$SECURITY;S:$SSID;P:$PASSWORD;;"
