# Wi-Fi QR Generator (macOS)

A simple macOS script that retrieves your **current Wi-Fi SSID, password, and security type** and generates a **scannable Wi-Fi QR code** in the terminal.

---

## Features

* Detects current Wi-Fi network and password
* Detects security type (WPA, WEP, or open)
* Generates QR code for instant connection

---

## Requirements

* macOS
* `qrencode` installed (`brew install qrencode`)

---

## Usage

```bash
chmod +x ssid-pw-qr.sh
./wifi-qr.sh
```

Scan the displayed QR code with any phone to connect automatically.

---

## License

MIT License
