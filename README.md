# Recuperando a Senha do Root no Debian

Se você esqueceu a senha do usuário `root` no Debian, siga este procedimento para redefini-la com segurança.

---

## 🔧 Passo a Passo

### 1. Reinicie o computador

- No menu do **GRUB**, selecione a entrada padrão do Debian.
- Pressione a tecla **`e`** para editar.

---

### 2. Edite a linha do kernel

Encontre a linha que começa com:

```
linux /boot/vmlinuz...
```

No final dela, adicione:

```
init=/bin/bash
```

---

### 3. Inicie o sistema

- Pressione **Ctrl + X** ou **F10** para iniciar com o shell bash.

---

### 4. Remonte o sistema de arquivos com permissão de escrita

Digite no terminal:

```bash
mount -o remount,rw /
```

---

### 5. Redefina a senha do root

Digite:

```bash
passwd
```

Digite a nova senha duas vezes.

---

### 6. Reinicie o sistema

Execute:

```bash
exec /sbin/init
```

ou

```bash
reboot -f
```

---

## ✅ Pronto!

Você poderá acessar como root usando a nova senha.

---

## 🔒 Segurança adicional

Recomenda-se proteger o GRUB com senha para evitar que qualquer pessoa tenha acesso root através desse método.

