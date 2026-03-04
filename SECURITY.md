# Política de Seguridad

## ⚠️ Datos Sensibles

Este proyecto **NUNCA debe contener**:
- API Keys o tokens de autenticación
- Wallets o direcciones Bitcoin reales
- Contraseñas
- Nombres de usuarios/emails privados
- Datos financieros o montos reales

## 🔐 Buenas Prácticas

### Variables de Entorno
Para datos sensibles, usa siempre variables de entorno:

```bash
# Crear archivo .env (IGNORADO autom. por git)
NICEHASH_API_KEY=tu_key_aqui
NICEHASH_WALLET=tu_wallet_aqui
```

### Archivos a Ignorar
- `.env` - Variables de entorno locales
- `*.xlsx` - Reportes generados (pueden contener datos sensibles)
- `input_csvs/` - CSVs descargados
- `output/` - Reportes generados
- `processed/` - CSVs procesados

## 🚨 Si Expusiste Datos Accidentalmente

1. Notifica inmediatamente
2. Regenera credenciales/API keys
3. Revierte los commits que contienen datos sensibles

### Limpiar historial git:
```bash
git filter-branch --force --index-filter \
'git rm --cached --ignore-unmatch .env' \
--prune-empty --tag-name-filter cat -- --all
```

## ✅ Revisión de Seguridad

Antes de pushear, verifica:
```bash
# Buscar patrones sensibles
git diff --cached | grep -i 'password\|key\|secret\|token'

# Ver archivos a commitear
git diff --cached --name-only
```
