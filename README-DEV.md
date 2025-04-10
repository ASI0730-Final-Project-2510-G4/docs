# 🌿 **GitHub Flow Paso a Paso** 🌿

---

## 1. **Crear una Rama por Cada Issue** 🛠️

- **Formato del nombre**: `[tipo]/[issue-number]-[descripción-breve]`  
  _Ejemplo_: `feature/123-add-login-form` o `fix/456-resolve-responsive-bug`

```bash
git checkout -b feature/123-nombre-del-issue
```

---

## 2. **Realizar Cambios y Commits** 📝

Usa [**Conventional Commits**](https://www.conventionalcommits.org/en/v1.0.0/) para mensajes claros:

- `feat`: Nueva funcionalidad.
- `fix`: Corrección de errores.
- `docs`: Cambios en documentación.
- `style`: Ajustes de formato (sin afectar código).
- `refactor`: Mejoras de código sin cambiar funcionalidad.
- `test`: Añadir o modificar tests.
- `chore`: Tareas de mantenimiento (ej: dependencias).

**Ejemplo de commit**:

```bash
git commit -m "feat: añadir formulario de login"
git commit -m "fix: corregir validación de email"
```

---

## 3. **Subir Cambios a la Rama** 🚀

- **Primer push**: Configura el upstream con `-u` para vincular la rama local/remota.

```bash
git push -u origin feature/123-nombre-del-issue
```

- **Pushs siguientes**:

```bash
git push
```

---

# 🔄 **Paso Crítico Antes del PR: Sincronizar con Main** 🔄

**¡Evita conflictos al mergear!** 🚨

## **4. Sincronizar tu Rama con Main** 📥

**Sigue este flujo ANTES de crear el PR**:

1. **Cambia a la rama principal** (main/master):
   ```bash
   git checkout main
   ```
2. **Descarga los últimos cambios**:

   ```bash
   git pull origin main
   ```

3. **Vuelve a tu rama de trabajo**:

   ```bash
   git checkout feat/45-nombre-del-issue
   ```

4. **Mergea main en tu rama**:

   ```bash
   git merge main
   ```

   - ⚠️ **Si hay conflictos**:
     - Resuélvelos manualmente en tu editor de código.
     - Usa `git status` para identificar archivos en conflicto.

5. **Haz commit de la sincronización**:

   ```bash
   git commit -m "chore: merge main into feat/45-nombre-del-issue"
   ```

6. **Sube los cambios actualizados**:
   ```bash
   git push
   ```

### **¿Por qué es importante?** 💡

- ✅ **Reduce el riesgo de conflictos** durante el merge del PR.
- ✅ **Asegura que tu código funciona** con la última versión de `main`.
- ✅ **Agiliza la revisión**: Los revisores ven cambios limpios y actualizados.

---

## 5. **Crear el Pull Request (PR)** 🎯

- Dirígete a GitHub y haz clic en **"Compare & pull request"**.
- **Título del PR**: Usa el mismo formato que el issue (ej: `Feat: Login Form #123`).
- **Descripción**:
  - Explica los cambios realizados.
  - Vincula el issue con `Resolves #123` o `Closes #123`.
- **Reviewers**: Asigna a quien deba revisar el código.
- **Merge**: Una vez aprobado, fusiona con la rama principal (`main`/`master`/`develop`).

---

### **💡 Tips Adicionales**

- 🔄 **Actualiza tu rama** con `git pull origin main` antes de subir cambios.
- 🧹 Elimina ramas locales después del merge:
  ```bash
  git branch -d feature/123-nombre-del-issue
  ```
