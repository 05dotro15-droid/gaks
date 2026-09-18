# GAKS V30

- Bootstrap FCM independiente del bridge principal.
- Lee el token cacheado directamente desde GaksAndroid.
- Espera a que authUser/authDb estén listos y hace upsert en gaks_fcm_devices.
- Mantiene el flujo nativo Firebase confirmado en V29.
- versionCode 30 / versionName 1.0.30.
